
# Interior Design Voice AI Agent for Lead Management

This project is an automated solution built for **Interia**, a North Indian interior design firm specializing in turnkey residential projects. It enhances lead management through voice-driven interactions and seamless workflow integrations.

## Features

- **Automated Lead Retrieval:** Pulls new leads from Airtable based on their "To Be Called" (TBC) status.
- **Voice-Driven Qualification:** Employs Neha, a Vapi AI-powered voice agent, to assess leads through conversation.
- **Smart Call Handling:** Retries unanswered calls (up to two attempts) and categorizes leads based on outcomes.
- **Callback Scheduling:** Syncs with Google Calendar to manage follow-up requests.
- **Comprehensive Logging:** Tracks call details, transcripts, and metrics in Airtable.

## Technologies Used

- **[n8n](https://n8n.io/):** Orchestrates workflows.
- **[Vapi AI](https://vapi.ai/):** Drives the voice assistant, Neha.
- **[Twilio](https://www.twilio.com/):** Enables outbound calling.
- **[Airtable](https://airtable.com/):** Manages leads and call records.
- **[OpenAI](https://openai.com/):** Analyzes transcripts for lead qualification.
- **[Google Calendar](https://calendar.google.com/):** Schedules callbacks.

## Repository Structure

- `part1.json`: n8n workflow for starting outbound calls.
- `part2.json`: n8n workflow for processing call results and updates.
- `Technical Assessment for AI Engineer(2)_Interior_Design_Voice_AI_Agent.pdf`: Project brief.
- `success_evalution_AI_agent_call_back_logic_Prompt.txt`: Logic for lead qualification and callbacks.
- `summary_generating_prompt.txt`: Template for call summary generation.
- `Vapi_ai_voice_assistant_prompt.txt`: Defines Neha’s persona and dialogue.
- `airtable_link_for_lead_&_call_record_table.txt`: Link to Airtable base ([View Airtable](https://airtable.com/appzkdRdcQWQUSR5K/shrg2jXNa7pAVV492)).

## How It Works

1. **Outbound Call Workflow (`part1.json`):**
   - Runs hourly to fetch "TBC" leads from Airtable.
   - Neha initiates the first call via Vapi AI.
   - Updates lead status to "In progress" with attempt "#1" in Airtable.

2. **Call Result Processing (`part2.json`):**
   - Captures call data via Vapi AI webhooks.
   - Analyzes outcomes: retries unanswered calls, categorizes answered leads (Hot, Warm, Cold, Special Case), or marks as "Failed" after two attempts.
   - Logs call details to Airtable.

3. **Voice Agent: Neha**
   - Delivers a professional, consultative experience.
   - Asks about budget, location, timeline, scope, and property size.

## Installation & Setup

1. **Clone the Repository:**
   ```bash
   git clone <repository-url>
   cd interior-design-voice-ai-agent
   ```

2. **Set Up n8n:**
   - Install n8n locally (requires Node.js) or use the cloud version.
   - Import `part1.json` and `part2.json` into the n8n editor.

3. **Configure Airtable:**
   - Use the [Airtable base](https://airtable.com/appzkdRdcQWQUSR5K/shrg2jXNa7pAVV492).
   - Add your Airtable Personal Access Token to n8n credentials.

4. **Configure Vapi AI & Twilio:**
   - Sign up at [Vapi AI](https://vapi.ai/) and configure with `Vapi_ai_voice_assistant_prompt.txt`.
   - Set up a Twilio test number for outbound calls.

5. **Integrate OpenAI & Google Calendar:**
   - Add your OpenAI API key to n8n for transcript analysis.
   - Authenticate Google Calendar in n8n for scheduling.

## Usage

- **Start Workflow 1:** Activate the outbound call workflow in n8n.
- **Run Workflow 2:** Ensure the call result webhook is active.
- **Test the System:** Add leads with a "TBC" status in Airtable to trigger the automation.

### Why This Works
- **Improved Title:** "Interior Design Voice AI Agent for Lead Management" clarifies the project’s focus.
- **Concise Intro:** Combines the welcome and overview into a brief, impactful summary.
- **Readable Features:** Bullet points make features easy to scan.
- **Detailed Instructions:** Step-by-step setup ensures users can replicate the system.
- **Complete Coverage:** Includes all key sections (features, tech, structure, etc.) without redundancy.
