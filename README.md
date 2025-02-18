# Clinical Trial Matching System

Intelligent patient-trial matching system combining structured eligibility checks with AI-powered medical analysis.

## Key Features

- Dynamic clinical trial data fetching from clinicaltrials.gov
- Hybrid matching system (rule-based + LLM analysis)
- XML patient data processing
- Detailed eligibility explanations
- Excel/JSON output generation

## Matching Process

Trial Discovery
- Fetches actively recruiting trials via clinicaltrials.gov API

Core Matching
Performs 3-stage verification:
- Age/Gender checks
- Medical condition matching
- AI-powered exclusion analysis

Output Generation
Produces Excel/JSON files with:
- Eligible trial IDs
- Match confidence indicators
- Human-readable explanations

## Methodology Highlights

1.Two-Stage Verification
- First-pass rule-based filtering
- Secondary LLM analysis of complex criteria

2.AI Integration
- Uses GPT-3.5-turbo for:
- Free-text criteria interpretation
- Medication history analysis
- Temporal condition evaluation

## Setup & Usage

1.Install dependencies: (bash)
- pip install pandas requests openai openpyxl

2.Set OpenAI API key: (python)
- os.environ["OPENAI_API_KEY"] = "your-key-here" 

3.Run matching: (python)
- matcher.run_matching(
    input_xml="patient_data.xml",
    output_file="matches.xlsx"
  )

## Input Requirements

Patient data in structured XML format
```xml
<Patient>
  <ID>PT-001</ID>
  <Demographics>
    <DOB>1980-05-15</DOB>
    <Gender>Male</Gender>
  </Demographics>
  <MedicalConditions>
    <Condition>Diabetes Type II</Condition>
  </MedicalConditions>
</Patient>

