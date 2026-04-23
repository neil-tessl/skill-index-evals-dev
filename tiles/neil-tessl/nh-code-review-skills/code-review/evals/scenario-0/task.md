# Code Review: User Search Endpoint

## Problem/Feature Description

A junior developer on your team has submitted a pull request adding a new user search endpoint to an internal admin API. The endpoint queries the database for users matching a search term and returns the results. The team lead is busy and has asked you to review the PR and leave comments directly in a review file.

The codebase uses Python with a PostgreSQL database. The change is relatively small but touches the data layer, so thoroughness matters. Your review will be the only gate before this merges.

## Output Specification

Write your complete code review to a file named `review.md`. The review should cover the code provided below and include all feedback you have for the author.

## Input Files

The following file represents the change being reviewed. Extract it before beginning.

=============== FILE: inputs/user_search.py ===============
import psycopg2

def search_users(conn, query):
    cursor = conn.cursor()
    sql = "SELECT id, username, email FROM users WHERE username LIKE '%" + query + "%'"
    cursor.execute(sql)
    rows = cursor.fetchall()
    results = []
    for row in rows:
        results.append({"id": row[0], "username": row[1], "email": row[2]})
    return results
