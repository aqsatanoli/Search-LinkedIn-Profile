# LinkedIn Profile Search Agent

An automated workflow built with n8n that allows you to search LinkedIn profiles from a runtime query and store structured results (Name, Role, LinkedIn URL, Snippet) into Google Sheets.This project integrates SerpAPI for Google-powered LinkedIn search and Google Sheets API for storing results in real time.

# Key Features

  Dynamic Input – Users enter search prompts and desired number of results via an n8n Form Trigger

 Smart Query Builder – Automatically formats queries for LinkedIn searches using Google Search

SerpAPI Integration – Reliable, structured search results from Google SERP

Google Sheets Storage – Results are appended directly into your connected Google Sheet

Clean Data Extraction – Extracts and organizes Name, Role, LinkedIn URL, and Snippet

# Tech Stack

n8n: Workflow automation engine

SerpAPI: Google Search API

Google Sheets API: Data storage

JavaScript (Code Node): Data filtering and transformation

# Workflow Overview

Form Submission

User provides:

Prompt (e.g., CEO fintech New York)

Result (number of profiles to fetch)

Set Search Query

Prepares query parameters for SerpAPI

HTTP Request (SerpAPI)

Calls Google Search with LinkedIn filters

Code Node

Extracts LinkedIn profile data from search results

Append Row in Google Sheets

Saves structured results into your sheet

# Example

Form Input

Prompt: CTO Artificial Intelligence London
Result: 10


# Google Sheets Output

Name	Role	LinkedIn	Snippet
JohnDoe	CTO at AI Labs	https://linkedin.com/in/johndoe CTO driving innovation in AI...
JaneSmith	Chief Technology Officer	https://linkedin.com/in/janesmith Experienced leader in ML and AI...
# Getting Started
1. Clone Repository
git clone https://github.com/<your-username>/linkedin-profile-search-agent.git
cd linkedin-profile-search-agent

2. Run n8n

You can run n8n locally or with Docker.

Local (npm):

npm install -g n8n
n8n start


Docker:

docker run -it --rm \
  -p 5678:5678 \
  -v ~/.n8n:/home/node/.n8n \
  n8nio/n8n

3. Configure Environment

Get your SerpAPI key → SerpAPI Dashboard

Add the API key in the Set Search Query node

Connect your Google Sheets credentials in the Append Row in Sheet node

4. Import Workflow

Open n8n at http://localhost:5678

Import the provided JSON workflow (linkedin-profile-agent.json)

Activate the workflow
