# Automated-Ticket-Routing-and-SLA-Monitoring-for-Zendesk

This project streamlines Zendesk ticket management by automatically prioritizing support requests and monitoring SLA compliance.

Problem Statement

Manually tracking and triaging tickets can lead to delays, SLA breaches, and poor customer experience. High-priority tickets (VIP or urgent) require immediate attention, while normal tickets should still be monitored for overdue conditions. This workflow reduces manual effort by automating ticket handling and alerting.

Key Features

Automatic Ticket Tagging: Identifies and assigns tags to urgent and normal tickets.

SLA Monitoring: Tracks ticket response times to avoid SLA violations.

Overdue Alerts: Sends Slack notifications when tickets are overdue.

Priority Handling: Ensures urgent tickets are escalated to the right channel quickly.

Seamless Zendesk Integration: Connects directly with Zendesk for real-time updates.

KPIs Tracked

Number of urgent tickets tagged

Number of normal tickets tagged

Overdue tickets detected

SLA compliance rate

Response time for urgent tickets

Workflow Overview

The workflow is built in n8n and consists of the following steps:

Trigger Node – Starts the workflow when new tickets are created or updated.

Compute Thresholds – Defines SLA deadlines for urgent and normal tickets.

IF Node (Urgency Check) – Splits tickets into Urgent or Normal.

True (Urgent): Tickets tagged as urgent and sent for escalation.

False (Normal): Tickets tagged as normal and monitored for SLA.

Zendesk Update Nodes – Updates ticket tags in Zendesk.

Overdue Check – Compares ticket age with SLA thresholds.

Slack Node – Sends notifications to the support team for overdue or urgent tickets.

Tools & Technologies

n8n: Workflow automation tool

Zendesk: Customer support ticketing system

Slack: Team collaboration and notification platform

How to Use

Import the workflow JSON into your n8n instance.

Connect your Zendesk and Slack credentials in n8n.

Adjust SLA thresholds as per business needs.

Activate the workflow to automatically monitor tickets.

Check Slack for overdue alerts and Zendesk for updated tags.

Benefits

Reduced SLA breaches

Faster resolution for urgent issues
