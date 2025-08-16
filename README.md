# Automated-Ticket-Routing-and-SLA-Monitoring-for-Zendesk

This project streamlines Zendesk ticket management by automatically prioritizing support requests and monitoring SLA compliance.

Problem Statement:

Manually tracking and triaging tickets can lead to delays, SLA breaches, and poor customer experience. High-priority tickets (VIP or urgent) require immediate attention, while normal tickets should still be monitored for overdue conditions. This workflow reduces manual effort by automating ticket handling and alerting.

Key Features:

Automatic Ticket Tagging: Identifies and assigns tags to urgent and normal tickets.

SLA Monitoring: Tracks ticket response times to avoid SLA violations.

Overdue Alerts: Sends Slack notifications when tickets are overdue.

Priority Handling: Ensures urgent tickets are escalated to the right channel quickly.

Seamless Zendesk Integration: Connects directly with Zendesk for real-time updates.

KPIs Tracked:

Number of urgent tickets tagged

Number of normal tickets tagged

Overdue tickets detected

SLA compliance rate

Response time for urgent tickets

Workflow Overview:

Trigger Node

Starts the workflow when a new ticket is created or updated in Zendesk.

Compute SLA Thresholds (Set Node)

Defines the SLA limits (e.g., urgent tickets = 1 hr, normal tickets = 24 hrs).

This is where you establish the "deadline" logic.

IF Node – Urgency Check

Looks at the ticket’s priority or tags.

Branches into two flows:

True (Urgent branch)

Updates the ticket in Zendesk with the "urgent" tag.

Runs overdue check specific to urgent SLA threshold.

If overdue → sends a Slack alert to the urgent channel.

False (Normal branch)

Updates the ticket in Zendesk with the "normal" tag.

Runs overdue check specific to normal SLA threshold.

If overdue → sends a Slack alert to the general support channel.

Zendesk Update Nodes

Apply tags ("urgent" or "normal") directly in Zendesk.

These are separate nodes for each branch.

Overdue Check (IF / Compare Node)

Compares current time vs. ticket creation/last update.

If ticket age > SLA threshold → triggers escalation.

Slack Notification Nodes

Sends alert messages to Slack.

Different channels/messages based on urgency.

Tools & Technologies:

n8n: Workflow automation tool

Zendesk: Customer support ticketing system

Slack: Team collaboration and notification platform

How to Use:

Import the workflow JSON into your n8n instance.

Connect your Zendesk and Slack credentials in n8n.

Adjust SLA thresholds as per business needs.

Activate the workflow to automatically monitor tickets.

Check Slack for overdue alerts and Zendesk for updated tags.

Benefits:

Reduced SLA breaches

Faster resolution for urgent issues
