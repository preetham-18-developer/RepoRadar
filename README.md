# RepoRadar

RepoRadar is an automation system that delivers a daily digest of trending GitHub repositories to subscribed developers. The system collects subscriber emails through a web interface, stores them in Google Sheets, and sends a curated list of repositories every morning using automated workflows built with n8n.

The goal of this project is to demonstrate practical workflow automation by integrating APIs, cloud services, and scheduled tasks into a complete end-to-end system.



## Overview

Developers often miss interesting open-source projects because of the volume of repositories created on GitHub each day. RepoRadar addresses this problem by automatically collecting highly starred repositories and distributing them to subscribers as a daily email digest.

The system consists of two independent workflows:

1. **Subscription Workflow**
   - Collects user emails through a web form
   - Stores subscriber information in Google Sheets

2. **Daily Digest Workflow**
   - Fetches trending repositories from the GitHub API
   - Formats repository details
   - Sends an email digest to all subscribers


## System Architecture
WORKFLOW-1:
Frontend (Subscription Form)  
        │  
        ▼  
n8n Webhook  
        │  
        ▼  
Google Sheets (Subscriber Database)

WORKFLOW-2:
Scheduled Workflow (Daily 09:00)  
        │  
        ▼  
GitHub API  
        │  
        ▼  
Repository Formatting Logic  
        │  
        ▼  
Email Delivery to Subscribers



## Features

- Automated daily GitHub repository discovery
- Email-based developer newsletter
- Subscriber management using Google Sheets
- Fully automated workflows using n8n
- API integration with GitHub
- Scheduled execution using workflow triggers



## Technologies Used

- **n8n** – Workflow automation platform  
- **GitHub API** – Repository search and data retrieval  
- **Google Sheets API** – Subscriber storage  
- **HTML / CSS / JavaScript** – Subscription interface  
- **Gmail Integration** – Email delivery  


## Workflows

### 1. Subscriber Registration

The subscription workflow collects developer emails through a frontend form and stores them in Google Sheets.

Flow:

Frontend Form → n8n Webhook → Google Sheets

Captured data includes:

- Name  
- Email  
- Subscription timestamp  



### 2. Daily Repository Digest

A scheduled workflow runs every morning and sends repository recommendations to all subscribers.

Flow:

Schedule Trigger → GitHub API → Data Processing → Google Sheets → Email Delivery

Steps performed:

1. Fetch repositories using the GitHub Search API  
2. Select top repositories based on star count  
3. Format repository details  
4. Retrieve subscriber emails  
5. Send a formatted email digest  


## Example Email Content

Subject:

RepoRadar – Daily GitHub Repository Digest

Body:

Top GitHub Projects Today

1. repository-name  
Description of the project  
https://github.com/user/repository

2. repository-name  
Description of the project  
https://github.com/user/repository



## Project Structure

RepoRadar

│  
├── frontend  
│   ├── index.html  
│   ├── styles.css  
│   └── script.js  

├── workflows  
│   ├── subscription-workflow.json  
│   └── daily-digest-workflow.json  

└── README.md  



## Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/reporadar.git
cd reporadar
```

### 2. Configure n8n

1. Import the workflow files into n8n  
2. Configure credentials for:
   - Google Sheets
   - Gmail
3. Update the webhook URL in the frontend form  

### 3. Deploy the Frontend

The subscription page can be hosted using GitHub Pages or any static hosting service.


## Future Improvements

- Repository summaries using language models  
- Filtering repositories by programming language  
- Web dashboard for subscriber management  
- Analytics for email engagement  
- Advanced ranking of trending repositories  



## Author

Preetham Goud
Computer Science Student and Developer


