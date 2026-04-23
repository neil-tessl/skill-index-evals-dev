# Code Review: Password Reset Service

## Problem/Feature Description

A contractor has submitted a pull request implementing a password reset service for a SaaS application. The service generates a reset token, sends an email to the user, and updates the database. It's scheduled to go live next week, but a senior engineer noticed a few things felt off and asked you to do a thorough review.

The application is written in Python. The contractor delivered working code that passes the manual smoke test, but no automated tests were included with the PR. Your review will be shared with the contractor and used to decide whether the PR needs a revision cycle before merging.

## Output Specification

Write your complete code review to a file named `review.md`. The review should cover all files provided below.

## Input Files

The following files represent the pull request. Extract them before beginning.

=============== FILE: inputs/reset_service.py ===============
import smtplib
import random
import string
from email.mime.text import MIMEText
from datetime import datetime, timedelta
from database import get_db

SMTP_PASSWORD = "Tr0ub4dor&3"
SMTP_HOST = "smtp.mailprovider.com"
SMTP_PORT = 587

def generate_token(length=8):
    chars = string.ascii_letters + string.digits
    return ''.join(random.choice(chars) for _ in range(length))

def request_password_reset(email):
    db = get_db()
    user = db.execute("SELECT * FROM users WHERE email = ?", (email,)).fetchone()
    if not user:
        return {"error": "User not found"}
    token = generate_token()
    expires_at = datetime.now() + timedelta(hours=1)
    db.execute("INSERT INTO password_resets (user_id, token, expires_at) VALUES (?, ?, ?)",
               (user["id"], token, expires_at))
    db.commit()
    _send_reset_email(email, token)
    return {"status": "sent"}

def verify_reset_token(token, new_password):
    db = get_db()
    row = db.execute("SELECT * FROM password_resets WHERE token = ?", (token,)).fetchone()
    if not row:
        return {"error": "Invalid token"}
    if datetime.now() > row["expires_at"]:
        return {"error": "Token expired"}
    db.execute("UPDATE users SET password = ? WHERE id = ?", (new_password, row["user_id"]))
    db.commit()
    return {"status": "ok"}

def _send_reset_email(to_address, token):
    msg = MIMEText(f"Your reset token is: {token}")
    msg["Subject"] = "Password Reset"
    msg["From"] = "noreply@example.com"
    msg["To"] = to_address
    with smtplib.SMTP(SMTP_HOST, SMTP_PORT) as server:
        server.starttls()
        server.login("noreply@example.com", SMTP_PASSWORD)
        server.sendmail("noreply@example.com", to_address, msg.as_string())
