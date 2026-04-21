# Automated Appointment Reminder Call Campaign

## Problem/Feature Description

A healthcare clinic called Clearview Medical runs a weekly batch of appointment reminder calls to patients. Each patient needs to hear a personalized greeting that uses their name and mentions the specific date and time of their upcoming appointment. The clinic already has an ElevenLabs voice agent configured with a reminder script, but needs a Python script that loops through a list of patients and places a personalized outbound call to each one.

The calls should be placed via the clinic's Twilio integration. If a call fails (network error, Twilio rejection, etc.) the script should log the error and continue with the next patient — the clinic must not miss reminders for other patients just because one call failed. Each successful call should have its conversation ID printed so the operations team can cross-reference with call logs later.

## Output Specification

Produce a single file:

- `send_reminders.py` — Python script that places outbound reminder calls for the patient list provided below. The script should personalize each call with the patient's name and appointment details. Read the ElevenLabs API key from the environment — do not hardcode it.

## Input Files

The following files are provided as inputs. Extract them before beginning.

=============== FILE: inputs/patients.json ===============
[
  {
    "name": "Sarah Chen",
    "phone": "+12025550101",
    "appointment_date": "Thursday, April 24",
    "appointment_time": "10:30 AM"
  },
  {
    "name": "Marcus Rivera",
    "phone": "+13105550182",
    "appointment_date": "Friday, April 25",
    "appointment_time": "2:15 PM"
  },
  {
    "name": "Priya Nair",
    "phone": "+17185550147",
    "appointment_date": "Monday, April 28",
    "appointment_time": "9:00 AM"
  },
  {
    "name": "James Okoye",
    "phone": "+16175550193",
    "appointment_date": "Monday, April 28",
    "appointment_time": "3:45 PM"
  }
]

Use the following placeholder IDs in your script (the real values would be configured in a deployment environment):
- Agent ID: `agent_clearview_reminder`
- Phone number ID: `phone_clearview_main`
