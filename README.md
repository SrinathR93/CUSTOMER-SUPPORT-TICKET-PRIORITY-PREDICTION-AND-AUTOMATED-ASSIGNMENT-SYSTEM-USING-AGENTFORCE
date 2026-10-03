# Customer Support Ticket Priority Prediction and Automated Assignment System Using Agentforce

## 📌 Project Overview

The **Customer Support Ticket Priority Prediction and Automated Assignment System** is a Salesforce-based solution designed to improve customer support operations by automating ticket priority analysis and support assignment.

The system uses **Salesforce, Agentforce, and Salesforce Flow** to analyze customer support ticket descriptions, determine the appropriate priority level, and support automated handling of high-priority tickets.

The goal is to reduce manual effort, improve response time, and help support teams handle urgent customer issues more efficiently.

---

## 🎯 Objectives

* Automate customer support ticket priority classification.
* Identify high-priority and urgent support issues.
* Reduce manual ticket prioritization.
* Support appropriate assignment of tickets to support staff.
* Create automated tasks for high-priority tickets.
* Track ticket status and resolution information.
* Monitor SLA breach risks.
* Improve support team productivity and customer satisfaction.

---

## 🚨 Problem Statement

Support teams may receive a large number of customer tickets every day. When tickets are manually reviewed and assigned:

* Urgent issues may not be identified quickly.
* Tickets can be assigned to inappropriate support levels.
* Workloads may become uneven.
* Response and resolution times can increase.
* Support managers may have limited visibility into ticket priorities and SLA risks.

This project addresses these challenges by introducing automation using Salesforce and Agentforce.

---

## 💡 Proposed Solution

The system provides a centralized Salesforce-based ticket management solution.

### Basic Workflow

```text
Customer Support Ticket
          ↓
Salesforce
          ↓
Ticket Description Analysis
          ↓
Agentforce
          ↓
Priority Determination
          ↓
┌─────────┼─────────┐
↓         ↓         ↓
High    Medium     Low
↓         ↓         ↓
Urgent   Normal    Normal
Task     Handling  Handling
↓
Support Assignment
```

Agentforce analyzes the ticket information and determines the appropriate priority. Salesforce Flow performs the required automation and supports ticket handling.

---

## 🛠️ Technologies Used

| Technology            | Purpose                                             |
| --------------------- | --------------------------------------------------- |
| Salesforce            | Main CRM and application platform                   |
| Agentforce            | AI-based ticket analysis and priority determination |
| Salesforce Flow       | Backend automation and ticket processing            |
| Salesforce Tasks      | Handling actions for high-priority tickets          |
| Salesforce Reports    | Ticket and support performance analysis             |
| Salesforce Dashboards | Visual monitoring and management insights           |

---

## 🗂️ Data Model

The project uses a custom Salesforce object:

**Support Ticket Intelligence**

API Name:

```text
Support_Ticket_Intelligence__c
```

### Main Fields

| Field           | Type            | Purpose                          |
| --------------- | --------------- | -------------------------------- |
| Ticket Number   | Auto Number     | Unique ticket identifier         |
| Customer        | Lookup(Account) | Links ticket to customer account |
| Contact         | Lookup(Contact) | Identifies customer contact      |
| Issue Type      | Picklist        | Technical, Billing, General      |
| Description     | Long Text Area  | Stores customer issue details    |
| Priority Level  | Picklist        | Low, Medium, High                |
| Status          | Picklist        | New, In Progress, Resolved       |
| Created Date    | Date            | Ticket creation date             |
| Assigned To     | Lookup(User)    | Assigned support user            |
| SLA Breach Risk | Checkbox        | Identifies possible SLA risk     |
| Resolution Time | Number          | Tracks resolution duration       |

---

## 🤖 Agentforce

The project includes an Agentforce sub-agent:

**Support Ticket Priority Analysis**

API Name:

```text
Support_Ticket_Priority_Analysis
```

### Agentforce Responsibilities

* Request the Account Name.
* Retrieve the latest support ticket.
* Analyze the ticket description.
* Determine the ticket priority.
* Trigger the approved Flow for high-priority tickets.
* Support appropriate support-level assignment.
* Return the processing result to the user.

Agentforce is restricted to the defined ticket-priority and assignment use case.

---

## 🔄 Salesforce Flow

The project uses an **Auto-Launched Flow** for backend automation.

### Flow Process

```text
Input Account Name
        ↓
Get Account
        ↓
Get Latest Support Ticket
        ↓
Analyze Description
        ↓
Determine Priority
        ↓
Create/Process Required Action
        ↓
Assign Appropriate Support Level
        ↓
Return Action Message
```

### Priority Logic

| Ticket Description                             | Priority |
| ---------------------------------------------- | -------- |
| Contains `urgent`, `not working`, or `failure` | High     |
| Contains `issue`, `slow`, or `delay`           | Medium   |
| Other descriptions                             | Low      |

For high-priority tickets, the system creates an **Urgent Ticket Handling** task.

---

## 👥 Users and Stakeholders

### Customer

* Submit support requests.
* Provide issue details.
* Receive timely attention for urgent issues.

### Support Agent

* View assigned tickets.
* Identify ticket priority.
* Update ticket status.
* Handle critical support requests.

### Support Manager

* Monitor ticket status.
* Monitor workload.
* Track SLA risks.
* View reports and dashboards.

### Agentforce

* Analyze ticket information.
* Determine ticket priority.
* Invoke approved automation.
* Return processing results.

---

## 🔐 Security Model

The system follows role-based access according to user responsibilities.

| User            | Access                                                              |
| --------------- | ------------------------------------------------------------------- |
| Customer        | Create requests and view relevant information                       |
| Support Agent   | View assigned tickets and update status                             |
| Support Manager | Monitor tickets, workload, reports and dashboards                   |
| Agentforce      | Analyze permitted ticket information and invoke approved automation |

The objective is to ensure that users access only the information and actions required for their responsibilities.

---

## 📊 Expected Benefits

* Faster identification of urgent tickets.
* Reduced manual prioritization.
* Improved support assignment.
* Better workload management.
* Improved visibility of SLA risks.
* Increased support team productivity.
* Better customer support response.

---

## 📁 Project Structure

```text
customer-support-ticket-agentforce/
│
├── README.md
│
├── Documentation/
│   └── Phase-1-Requirement-Analysis.pdf
│
├── Salesforce/
│   ├── Custom-Objects/
│   ├── Custom-Fields/
│   ├── Flows/
│   └── Agentforce/
│
└── Demo/
    └── Project-Demo-Video-Link.txt
```

> The folder structure can be updated according to the Salesforce metadata and documentation uploaded to this repository.

---

## 🚀 Project Outcome

This project demonstrates how **Salesforce automation and Agentforce** can be combined to support intelligent customer support ticket management.

The solution focuses on automatically analyzing ticket information, determining priority, supporting appropriate assignment, and creating actions for urgent issues.

---

## 👨‍💻 Project Information

**Project Title:**
Customer Support Ticket Priority Prediction and Automated Assignment System Using Agentforce

**Platform:** Salesforce

**AI Platform:** Agentforce

**Automation:** Salesforce Flow

**Project Type:** Naan Mudhalvan – Project Development

---

## 📄 Documentation

The repository contains the project requirement analysis and supporting documentation related to the Salesforce and Agentforce implementation.

---

## ⭐ Future Enhancements

Potential future enhancements include:

* Advanced AI-based priority prediction.
* Intelligent workload balancing.
* More advanced SLA breach prediction.
* Automated customer notifications.
* Support performance analytics.
* Integration with external support channels.
* Historical ticket-based AI analysis.
