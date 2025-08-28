# CollegenceAI

CollegenceAI is an n8n workflow repository that helps students navigate the U.S. college admission process. It includes:

1. A **form workflow** that collects student details from a form and stores them in Airtable.  
2. An **AI agent workflow** that uses the student data and multiple Airtables as tools to provide personalized guidance on college admissions, extracurriculars, awards, scholarships, and application timelines.

The AI agent is designed to be friendly, personalized, and able to provide actionable advice based on the student’s profile.

---

## Repository Structure

```
CollegenceAI/
├─ CollegenceAI.json              # n8n workflow file containing both workflows
├─ README.md                      # This file
├─ CollegenceAIAirtables/         # Folder containing Airtable CSV files
│   ├─ StudentDetails.csv
│   ├─ Awards.csv
│   ├─ Extracurriculars.csv
│   ├─ Majors.csv
│   ├─ CollegeList.csv
│   ├─ ScholarshipsForUser.csv
│   ├─ ProgramsDatabase.csv
│   ├─ ScholarshipsDatabase.csv
│   └─ CollegesDatabase.csv
```

---

## Setting Up Airtable

1. **Download the CSV files** from the `CollegenceAIAirtables` folder.  
2. **Import each CSV into Airtable**:  
   - Go to [Airtable](https://airtable.com/) and log in.  
   - Click **"Add a base → Import a spreadsheet"**.  
   - Select one CSV file and import it.  
   - Repeat for all 9 CSV files.  

> Make sure the table names and column headers match exactly as in the CSVs, since the workflows reference these names.

3. After importing, note your **Airtable API key** and **base IDs**, which you will use in n8n credentials.

---

## Setting Up n8n

1. **Install n8n** if you haven't already:  
```bash
npm install n8n -g
```

2. **Import the workflow**:  
   - Open n8n.  
   - Click **"Import" → select `CollegenceAI.json`**.  
   - This JSON contains **both workflows**: the form workflow and the AI agent workflow.

3. **Set up credentials for Airtable**:  
   - Go to **Credentials** in n8n.  
   - Add a new Airtable credential with your **API key** and link it to each base you imported.

4. **Optional tools**:  
   - Google Calendar (used for adding deadlines). Add credentials if you want the AI to manage calendar events.

---

## Using the Workflows

### **1. Form Workflow**
- Collects student information via a form.  
- Populates 4 Airtables: Student Details, Extracurriculars, Awards and Majors, which are then used as inputs for the AI agent.  
- Ensure students fill out the form accurately, as the AI agent reads this data to provide personalized guidance.

### **2. AI Agent Workflow**
The AI agent uses the following Airtables as **tools**:

- **Student Details**: Contains student profile (name, GPA, major, location, college preferences). Used to personalize responses.  
- **ECs / Awards / Programs / Scholarships / Colleges / Majors**: Used to rank activities, suggest new opportunities, provide college recommendations, and suggest scholarships.  
- **College List & ECs Update / Scholarships Update**: Used to record recommendations and updates from the agent.  
- **Google Calendar**: Optional; used to add college and scholarship deadlines if requested.

**Core Abilities**:

1. Read, evaluate, and rank a student's extracurricular activities (ECs) and awards based on admission value.  
2. Suggest new extracurricular opportunities from your own knowledge or the Programs Airtable.  
3. Provide college recommendations using the Colleges Airtable or external knowledge. Compare colleges using fields from the Colleges Airtable.  
4. Suggest scholarships using your knowledge or the Scholarships Airtable.  
5. Personalize all recommendations using data from Student Details.  
6. Ask if the user wants deadlines added to Google Calendar and add early action/regular decision deadlines.  
7. Explain the U.S. college admission process.  
8. Provide a personalized application timeline based on student data and ECs.

---

## Quick Tips

- Ensure all CSVs are imported into Airtable correctly.  
- The workflows will break if table names or field headers do not match exactly.  
- Keep your Airtable API key secure.  
- For Google Calendar integration, provide proper credentials if you want deadlines automatically added.  

---

## License

This repository is provided for educational purposes. You may use and modify the workflows for your own college admissions planning.
