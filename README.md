# Enterprise-ICP-Qualifier-and-Research-Agent

An AI-powered enterprise research and lead qualification workflow built using **n8n, OpenAI, Serper API, Webhooks, and Google Sheets**. The workflow automates company research, gathers relevant information from multiple web sources, evaluates prospects against an Ideal Customer Profile (ICP), and stores the qualification output in a Google Sheet.

## Overview

Manually researching enterprise prospects can be time-consuming. This project uses an AI agent to streamline the process by combining website research, news search, structured AI output, and automated data storage in a single workflow.

## Key Features

- **Webhook Integration:** Accepts incoming requests to initiate the research workflow.
- **Automated Website Research:** Fetches company homepage and About page information.
- **News Research:** Uses the Serper API to retrieve relevant company news and search results.
- **AI-Powered ICP Qualification:** Uses an OpenAI chat model to analyze collected information and assess a company's fit against the target customer profile.
- **Structured Output:** Uses an ICP Output Parser to organize the qualification results into a structured format.
- **Automated Data Storage:** Appends the generated results to Google Sheets for tracking and further analysis.

## Workflow Architecture

The workflow consists of two main stages:

### 1. Ingest & Research

1. **Webhook:** Receives the incoming request and starts the workflow.
2. **Fetch Homepage:** Retrieves information from the company's homepage.
3. **Fetch About Page:** Collects additional company information.
4. **Serper News Search:** Searches the web for relevant company news and research information.

### 2. Qualify & Store

5. **ICP Qualifier Agent:** Analyzes the collected research using the OpenAI Chat Model.
6. **ICP Output Parser:** Structures the agent's output for consistent downstream processing.
7. **Google Sheets Integration:** Appends the qualification results to a Google Sheet.

## Technology Stack

| Technology | Purpose |
|---|---|
| n8n | Workflow orchestration and automation |
| OpenAI | AI-powered company analysis and qualification |
| Serper API | Web search and company news research |
| Webhooks | Workflow triggering and request handling |
| Google Sheets API | Storing qualification results |
| Structured Output Parser | Formatting AI-generated results |

## How It Works

1. An incoming request triggers the n8n webhook.
2. The workflow collects company information from its website.
3. Serper retrieves additional information from web search and news results.
4. The ICP Qualifier Agent analyzes the available research.
5. The output parser formats the qualification results.
6. The workflow appends the results to Google Sheets.

This creates an automated pipeline from company research to structured prospect qualification and recordkeeping.

## Prerequisites

Before running the workflow, ensure you have:

- An n8n instance (cloud or self-hosted).
- An OpenAI API key and access to a supported chat model.
- A Serper API key.
- A Google account with access to Google Sheets.
- A configured Google Sheets credential in n8n.
- A configured webhook node and the required workflow connections.

## Setup and Configuration

1. Import or recreate the workflow in n8n.
2. Configure the Webhook node to accept the required company information.
3. Configure the homepage and About page research nodes.
4. Add your Serper API credentials to the news search node.
5. Connect your OpenAI credentials to the ICP Qualifier Agent.
6. Configure the ICP qualification instructions and output parser.
7. Connect Google Sheets and map the structured output to the appropriate columns.
8. Test the workflow with sample company information.
9. Activate the workflow and use the production webhook URL when ready.

**Security note:** Store API keys and credentials using n8n's credential management. Do not commit API keys, private webhook URLs, or other secrets to GitHub.

## Expected Outcome

For each successfully processed request, the workflow is designed to produce structured company research and ICP qualification results and append them to Google Sheets.

The exact qualification fields and scoring criteria depend on the agent's configured prompt and output schema.

## Potential Applications

- B2B sales prospecting
- Enterprise lead research
- Account qualification
- Sales pipeline research
- Business development automation
- AI-assisted market research

## Future Improvements

- Add configurable ICP scoring criteria.
- Introduce lead prioritization based on qualification scores.
- Add error handling and retry mechanisms.
- Prevent duplicate company entries.
- Integrate CRM platforms for downstream lead management.
- Add reporting dashboards for qualified prospects.

## Project Status

Developed as an AI workflow automation project using n8n, OpenAI, web search, and Google Sheets.
