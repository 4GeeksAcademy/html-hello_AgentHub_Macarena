# AgentHub Admin Dashboard - Specifications

## Project Overview

AgentHub is a SaaS platform that allows companies to rent AI agents for different business tasks. Administrators need a centralized dashboard to manage agents, customers, contracts, skills, and system activity.

The goal is to build a responsive admin dashboard using HTML, Tailwind CSS, and JavaScript with hardcoded data only.

---

## Layout

### Sidebar Navigation

A fixed sidebar visible on desktop containing:

- Dashboard
- Agents
- Customers
- Skills
- Contracts
- Error Logs
- Settings

The sidebar must support collapse/expand behavior.

---

### Top Navigation Bar

Contains:

- Search input
- Notifications button
- Dark mode toggle
- Administrator profile dropdown

---

## Dashboard Page

Display summary cards showing:

- Total Agents
- Active Contracts
- Registered Customers
- Monthly Revenue

Include:

- Recent activity feed
- Quick statistics section
- System status indicator

---

## Agents Management

Display a table of AI agents with:

- Name
- Category
- Status
- Assigned Skills
- Customer

Features:

- Search agents
- Filter by status
- Add Agent button
- Edit Agent modal
- Delete Agent confirmation modal

---

## Customers Management

Display a table with:

- Company Name
- Contact Person
- Email
- Active Contracts

Features:

- Search customers
- View details modal
- Edit customer modal

---

## Skills Management

Display all available AI skills as cards.

Each skill includes:

- Skill Name
- Category
- Usage Count

Features:

- Add skill modal
- Edit skill modal
- Delete skill confirmation

---

## Contracts Management

Display a contracts table containing:

- Contract ID
- Customer
- Agent
- Start Date
- End Date
- Status

Features:

- Search contracts
- Filter by status
- View contract details

---

## Error Logs

Display system logs table containing:

- Date
- Severity
- Agent
- Message

Features:

- Filter by severity
- Expand log details
- Clear logs button

---

## Settings

Settings section should include:

- Dark mode toggle
- Notification preferences
- Account settings

---

## Interactive Components

The project must include:

- Sidebar collapse/expand
- Dropdown menus
- Modal windows
- Search filters
- Dark mode
- Collapsible sections

---

## Responsive Design

Desktop:
- Full sidebar visible

Tablet:
- Reduced sidebar

Mobile:
- Sidebar becomes a drawer menu

All tables must be horizontally scrollable on small screens.

---

## Technical Requirements

- HTML
- Tailwind CSS
- Vanilla JavaScript
- No backend
- Hardcoded data
- Mobile-first approach
- Clean and modern UI
