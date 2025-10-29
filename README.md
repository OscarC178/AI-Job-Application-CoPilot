##  <img width="24" height="32" alt="robby_the_robot" src="https://github.com/user-attachments/assets/39922d9e-d13d-4daa-8a28-a6fc5d3eb59a" />[AI Job Application Co-pilot](https://docs.google.com/spreadsheets/d/1y3Wq9MOhnxDOnKdBUGCmHCM0mUxlVJ8rBPsZePj7Rv0/edit?gid=1204996861#gid=1204996861)
This project is a comprehensive, automated system designed to streamline the entire job application process—from discovering relevant roles on LinkedIn to generating tailored application materials. It combines a no-code web automation workflow with a powerful AI assistant built directly into Google Sheets.

The system automatically finds and saves relevant job listings, checks for duplicates, and then helps you craft a high-quality, customized application in minutes, not hours.

## ✨ Key Features
🤖 Automated Job Scraping: A workflow automatically scans LinkedIn for jobs matching your criteria (e.g., "Product Manager in London").

** deduplication:** The system checks if a job has already been saved to your sheet, preventing clutter.

👨‍💼 Hiring Manager Discovery: The workflow attempts to identify the most likely hiring manager for the job on LinkedIn.

📊 Centralized Dashboard: All potential jobs are saved to a Google Sheet, creating a single source of truth for your job hunt.

✍️ AI-Powered Analysis: A custom script uses the Google Gemini API to analyze each job description against your master CV.

📝 Content Generation: The AI generates a match score, tailored CV bullets, an outreach message, and predicted interview questions.

🔧 Fully Customizable: Prompts, CV, and API key are all managed in a user-friendly Settings sheet—no code-editing required.

## ⚙️ How It Works
The system operates in two distinct stages: Job Discovery and Application Tailoring.

### Part 1: Automated Job Discovery & Scraping (Relay.app)

<img width="1700" height="2500" alt="Scrape and Output linkedin only - Workflow - 2025-10-29 at 21 23 00" src="https://github.com/user-attachments/assets/4d8d2420-8ec6-4a82-b8eb-48a530a83525" />


This stage is handled by an automated workflow that runs independently to populate your Google Sheet with new opportunities.

Trigger: The workflow is initiated either manually or on a schedule (e.g., once a day).

Find Jobs: It searches LinkedIn for new job postings that match your predefined roles and location, and llm does some prefiltering to remove the roles that aren't related to your CV/ preferences as a second validation

Extract Details: It extracts key information from each job listing.

Loop & Process: For each job found, it performs the following steps:

It connects to your Google Sheet to check if the job already exists.

It searches LinkedIn for the most likely hiring manager associated with the role.

If the job is new, it adds a new row to the "Job Applications" sheet with all the scraped information (Job Title, Company, Description, Hiring Manager, etc.).


### Part 2: AI-Powered Analysis (Google Sheets)
Once the jobs are in the sheet, you take over with your AI co-pilot.

Select a Job: In the "Job Applications" sheet, you choose a row that the automation has added.

Run the Co-pilot: You select one of the options from the custom "Job Helper" menu.

API Call: The Apps Script reads the job description, your master CV, and your custom prompts from the Settings sheet. It then sends this data to the Google Gemini API for analysis.

Populate Results: The script receives the generated content from the AI and populates the corresponding cells in that row—filling out the match score, suggested CV bullets, and more.

Apply! You can now use this tailored content to confidently submit your application.

## 🛠️ Tech Stack
Automation/Scraping: Relay.app

Database & Frontend: Google Sheets

Backend & Logic: Google Apps Script (JavaScript)

AI Model: Google Gemini API (gemini-2.5-pro & gemini-2.5-flash)

## ![impatient](https://github.com/user-attachments/assets/841ab47c-b82a-4321-a4f8-84b16d5beec0) Getting Started
To set up your own version of this system, you will need to configure both the automation workflow and the Google Sheet.

### 1. Google Sheet Setup
Make a Copy: [Make your own copy of this Google Sheet](https://docs.google.com/spreadsheets/d/1y3Wq9MOhnxDOnKdBUGCmHCM0mUxlVJ8rBPsZePj7Rv0/edit?gid=1204996861#gid=1204996861).

Configure the Settings Tab:

Go to the Settings tab.

Paste your Google AI API Key into the correct cell.

Paste your Master CV text into the correct cell.

IMPORTANT: If you are not a Product Manager, edit the first line of the Pro Prompt Template to reflect your target role (e.g., "Software Engineer," "Marketing Manager" "Designer").

### 2. Automation Workflow Setup
Create the Workflow: In an automation tool like Relay.app, build the workflow as shown in the diagram above.

Connect Your Accounts: You may get a warning on the google sheet when you run it, this is to be expected, its to approve of the LLM adding and altering text into the Google Sheet. 

Schedule It: Set the workflow to run on a schedule that works for you (e.g., every morning).
