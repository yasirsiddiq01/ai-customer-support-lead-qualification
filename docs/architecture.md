# Architecture

## Overview

The workflow implements a controlled AI-assisted customer interaction pipeline in n8n.

AI is used for structured interpretation of customer requests, while deterministic workflow logic retains control over routing, scoring, escalation, and consequential communication.

## Processing Pipeline

```text
Webhook
   ↓
Input Validation
   ↓
Prepare AI Request
   ↓
Structured AI Analysis
   ↓
AI Output Validation
   ↓
Routing Confidence Policy
   ↓
Automated Routing Gate
   ↓
Intent Router
   ├── Sales
   ├── Support
   ├── FAQ
   └── Unknown
   ↓
Prepare Final Output
   ├── Webhook Response
   ├── Google Sheets Audit Log
   └── Gmail Draft Gate