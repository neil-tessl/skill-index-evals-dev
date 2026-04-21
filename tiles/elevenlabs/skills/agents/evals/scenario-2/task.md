# Automated Appointment Reminder Campaign for MediCall

## Problem/Feature Description

MediCall is a healthcare clinic network running an outbound appointment reminder campaign. Each morning, a script calls a list of patients to confirm or reschedule their upcoming appointments. Each call should greet the patient by name and mention their appointment details — but patients may provide sensitive information such as their date of birth or social security number during the call that should never appear in transcripts or be sent to the LLM (to avoid compliance issues).

Additionally, the clinic's compliance team requires that the agent cannot engage in off-topic conversations — if the agent starts to go off-script or discuss topics unrelated to appointments, the system should detect this and attempt to regenerate a better response (up to 3 times) before giving up. The feedback message injected during regeneration should reference why the response was blocked, using a template variable.

The campaign needs to route test calls to a staging agent branch and resolve environment-specific configuration from the staging workspace environment. Production calls use the default environment.

## Output Specification

Produce a Python script `outbound_campaign.py` that:

1. Iterates over the patient list provided below and initiates an outbound call for each patient
2. Personalizes each call with the patient's name and appointment time
3. Configures sensitive variable handling so that any value assigned from a tool response to `patient_dob` is not sent to the LLM or stored in the transcript
4. Routes calls where `is_test=True` to branch `branch_staging` with environment `staging`; all other calls use normal routing
5. Configures guardrails on the agent creation call to keep the conversation focused, with retry-based trigger action and a feedback template that references the blocking reason
6. Prints the conversation ID for each successfully initiated call

Assume the agent ID is stored in the environment variable `MEDIC_AGENT_ID` and the phone number ID in `MEDIC_PHONE_ID`.

## Input Files

The following patient data is provided. Extract it before beginning.

=============== FILE: inputs/patients.json ===============
[
  {"name": "Alice Torres", "phone": "+12025550101", "appointment_time": "Tuesday at 9:00 AM", "is_test": true},
  {"name": "Ben Okoro", "phone": "+12025550182", "appointment_time": "Wednesday at 2:30 PM", "is_test": false},
  {"name": "Celia Park", "phone": "+12025550139", "appointment_time": "Thursday at 11:00 AM", "is_test": false}
]
