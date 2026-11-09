# CCM Outreach Agent

> Voice AI for chronic-care-management (CCM) patient outreach — handles both **outbound and inbound** calls.

> **Note:** this repository contains documentation only — an overview and the workflow of the project. Source code and data are not included.

## Overview

A voice agent that calls patients enrolled in chronic care management — and answers their calls — and walks them through their monthly wellness questionnaire as a natural phone conversation. Inbound callers are verified first; outbound calls check for voicemail before the conversation starts.

## Workflow

```mermaid
flowchart TD
    O["<b>Outbound call</b><br/>automatic · scheduled callbacks · auto-redial"] --> M{"<b>Voicemail detection</b><br/>person or answering machine?"}
    M -- "answering machine" --> L["<b>Leave a callback message</b>"]
    M -- "person" --> Q
    I["<b>Inbound call</b><br/>patient calls in"] --> V["<b>Verify the patient's identity</b>"]
    V --> Q
    Q["<b>Conversation</b><br/>monthly wellness questionnaire as a natural phone conversation<br/><i>resume after dropped call · schedule a callback · hand-off to a human</i>"] --> S
    L --> S
    S["<b>Logs</b><br/>transcript, summary and outcome,<br/>reported back to the care platform"]
```

## Capabilities

- **Outbound calls** — placed automatically, including scheduled callbacks and auto-redial after a dropped call.
- **Inbound calls** — patients can call in and are verified before the questionnaire starts.
- **Identity verification** of inbound callers before any questions are asked.
- **Voicemail detection** on outbound calls — leaves a callback message instead of running the questionnaire on an answering machine.
- **Natural conversation** — the monthly wellness questionnaire is asked conversationally.
- **Resume after a dropped call**, **callback scheduling** and **hand-off to a human**.
- **Record keeping** — transcript, summary and outcome are saved and reported back to the care platform.

## Stack

Python · LiveKit · SIP telephony · LLM · Flask console · Docker

---

More projects: [github.com/ALIKAZMI001](https://github.com/ALIKAZMI001)
