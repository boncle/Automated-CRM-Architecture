# Automated CRM & Workflow Architecture

A decoupled, event-driven system built with Notion and n8n.

## 🤔 Why I Built This
About three years ago, I got really curious about how CRMs and automated email outreach systems actually worked behind the scenes. 

Since I already run my own self-hosted server environment and like tinkering with n8n automations, I decided to build my own CRM from scratch just to experiment with the concept. 

I built the logic completely intuitively—using Notion tables to organize people and tasks, splitting the automations into smaller workflows so they wouldn't break, processing records one by one to avoid crashing the system, and auto-filling email templates based on database updates. It started as a hands-on learning project just to see if I could figure out how to build a fully working system on my own.

-----

## 🏗️ Architecture
This system utilizes a modular, microservice approach:
- **Orchestration Layer:** Daily and Tasks Schedulers manage event timing.
- **Processing Layer:** Logic modules handle batch splitting and relational database joins.
- **Execution Layer:** Notion API triggers and SMTP email actions.

## 💡 Engineering Highlights
- **Governor Limit Awareness:** Batch processing (batch size: 1) to ensure system stability.
- **Decoupled Logic:** Sub-workflow orchestration to maintain clean, scalable code.
- **Relational Data Management:** Fuzzy comparison logic for multi-database lookups.

## 📂 Repository Contents
- `/workflows` contains the modular n8n JSON exports.