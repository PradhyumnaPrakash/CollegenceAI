# CollegenceAI n8n Workflows

## Overview
This repository contains two n8n workflows designed to help students navigate the U.S. college admission process with the assistance of a friendly AI agent.  

1. **Form Workflow:** Collects student data via a form and stores it in four Airtables.  
2. **AI Agent Workflow:** Uses the collected data, along with multiple Airtables, to provide personalized guidance, recommendations, and timelines for college applications, extracurriculars, scholarships, and majors.

---

## Airtables Used

| Airtable Name       | Purpose |
|--------------------|---------|
| Student Details     | Stores student profile information (GPA, test scores, major, location, college preferences, pronouns, application progress, etc.) |
| Extracurriculars    | Stores the student's extracurricular activities and awards for evaluation and ranking |
| Programs            | Database of extracurricular programs, internships, summer schools, and workshops |
| Scholarships        | Tracks scholarship opportunities relevant to the student |
| Majors              | Contains academic major information for personalized guidance |
| Colleges            | Stores college details for recommendations and deadline tracking |
| ECs Update          | Tracks new extracurricular activities suggested or added for the student |
| Scholarships Update | Tracks scholarships added to the student’s profile |
| College List        | Maintains a list of colleges recommended or selected by the student |

> **Note:** Users must create their own Airtables with matching table and field names for the workflow to function correctly. API keys must be set up in n8n credentials.

---

## Setup Instructions

1. **Clone or download** this repository.
2. **Import** the workflows into your n8n instance:
   - Open n8n → Workflows → Import → From File → Select the JSON file.
   - Both workflows are included in the same JSON file.
3. **Set up Airtable credentials** in n8n:
   - Add your Airtable API keys under n8n credentials.
4. **Ensure Airtable table names and fields** match those referenced in the workflows.
5. **Update webhook URLs** or other environment-specific values if needed.
6. **Run the workflows**:
   - Fill out the form workflow to input student data.
   - Use the AI agent workflow to interact with the student and provide guidance.

---

## AI Agent Capabilities

- Personalized evaluation of student extracurriculars and awards
- Suggestions for new programs, internships, and activities
- College recommendations, comparisons, and deadline tracking
- Scholarship discovery and updates
- Personalized application timeline and guidance

> The AI agent reads the student’s profile from Airtable and tailors all recommendations accordingly. It can also add college deadlines to Google Calendar if requested.

---

## Notes

- Make sure all Airtables are correctly set up with the appropriate structure and API keys.
- The workflows rely on multiple Airtables working together. Missing or misnamed tables/fields may cause errors.
- Google Calendar integration is optional and only triggered if the student requests deadlines to be added.
