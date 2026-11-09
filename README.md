# CCM Outreach Agent

> Voice AI for chronic-care-management (CCM) patient outreach — handles both **outbound and inbound** calls.

> **Note:** this repository contains documentation only — an overview and the workflow of the project. Source code and data are not included.

## Overview

A voice agent that calls patients enrolled in chronic care management — and answers their calls — and walks them through their monthly wellness questionnaire as a natural phone conversation. Inbound callers are identified and verified first; outbound calls check for voicemail before the conversation starts. Each call runs as either a Brief or a Detailed call.

## Workflow

```mermaid
flowchart TD
    O["<b>Outbound call</b><br/>automatic · scheduled callbacks · auto-redial"]
    I["<b>Inbound call</b><br/>patient calls in"]
    M{"<b>Voicemail detection</b><br/>person or answering machine?"}
    L["<b>Leave a callback message</b>"]
    V["<b>Patient determination</b><br/>identify and verify who is calling<br/><i>inbound calls only</i>"]
    T{"<b>Call style</b><br/>chosen per call"}
    B["<b>Brief call</b><br/>goals check-in · medication question<br/>anything to pass along to the doctor"]
    D["<b>Detailed call</b><br/>full monthly wellness questionnaire<br/>as a natural phone conversation"]
    W["<i>Throughout the call: resume after a dropped call<br/>schedule a callback · hand-off to a human</i>"]
    S["<b>Logs</b><br/>transcript, summary and outcome,<br/>reported back to the care platform"]
    O --> M
    M -- "answering machine" --> L
    M -- "person" --> T
    I --> V
    V --> T
    T -- "Brief" --> B
    T -- "Detailed" --> D
    B --> W
    D --> W
    W --> S
    L --> S
```

## Capabilities

- **Outbound calls** — placed automatically, including scheduled callbacks and auto-redial after a dropped call.
- **Inbound calls** — patients can call in and are verified before the questionnaire starts.
- **Patient determination (inbound only)** — inbound callers are identified and verified before any questions are asked. Outbound calls already know which patient they are dialling.
- **Voicemail detection** on outbound calls — leaves a callback message instead of running the questionnaire on an answering machine.
- **Brief and Detailed calls** — each call runs in one of two styles. *Brief* is short and to the point: a goals check-in, the medication question, then anything to pass along to the doctor. *Detailed* is the full monthly wellness questionnaire.
- **Natural conversation** — the questionnaire is asked conversationally.
- **Resume after a dropped call**, **callback scheduling** and **hand-off to a human**.
- **Record keeping** — transcript, summary and outcome are saved and reported back to the care platform.

## Stack

Python · LiveKit · SIP telephony · LLM · Flask console · Docker

---

More projects: [github.com/ALIKAZMI001](https://github.com/ALIKAZMI001)
