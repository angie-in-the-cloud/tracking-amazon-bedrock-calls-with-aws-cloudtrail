# Auditing AI: Tracking Amazon Bedrock Calls with AWS CloudTrail

A demonstration of how AWS CloudTrail logs Amazon Bedrock API activity and why that matters for GRC (governance, risk, and compliance).

> 📺 This repo accompanies my [YouTube video](https://youtu.be/LHOXhByqs7g)

---

## Overview

In GRC, the principle is simple: **if it's not logged, it didn't happen.** Without a record, there's no proof of compliance.

This project shows how CloudTrail captures Bedrock API calls to create an audit trail of AI usage across an AWS environment, using a simple Python chatbot built on the Bedrock Converse API.

---

## What This Demo Covers

- A Python script that calls the **Amazon Bedrock Converse API**
- How that API call appears in **AWS CloudTrail Event History**
- What CloudTrail records per event:
  - User identity details
  - Timestamp
  - Event name (e.g., `Converse`)
  - AWS region
- Why **prompts and model responses are NOT logged** - only the API call itself

---

## Key Governance Takeaway

CloudTrail gives visibility into *who used a model, when, and where*, without storing sensitive prompt content. That's auditability without privacy risk.

---

## Prerequisites

- An AWS account with Amazon Bedrock access
- IAM users configured with Bedrock permissions
- Python 3.x
- `boto3` installed
```bash
pip install boto3
```

---

## Usage

Run the chatbot script in your terminal to generate a Bedrock API call:
```bash
python chatbot.py
```

Then navigate to **AWS CloudTrail → Event History** and filter by:
- **Lookup attribute:** Event source
- **Value:** `bedrock.amazonaws.com`

Click on the `Converse` event to see all event details, such as: user identity details, timestamp, and region.

---

## Resources

📺 Watch the full walkthrough on YouTube: [YouTube](https://youtu.be/LHOXhByqs7g)

---
