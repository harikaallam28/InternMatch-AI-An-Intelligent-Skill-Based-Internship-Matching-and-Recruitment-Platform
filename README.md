🎓 InternMatch AI
Intelligent Skill-Based Internship Matching & Recruitment Platform

InternMatch AI is a Flask-based web application designed to connect students with suitable internship opportunities using a skill-based matching algorithm.

The platform allows internship providers to create opportunities by defining required skills and their importance, while students can apply by providing their CGPA, skills, projects, resume, and cover letter.

The system then calculates a personalized match score and provides an explanation of how the score was generated.

🚀 Key Features
👨‍🎓 Student Module

Student login and authentication

Browse available internships

Select an internship to apply for

Enter CGPA and project/achievement details

Provide skill ratings

Upload resume

Submit a cover letter

Receive an internship match score

View detailed match reasoning

Track application status

View whether an application is Pending, Selected, or Rejected

🏢 Internship Provider Module

Provider login

Create internship opportunities

Define internship title and type

Specify duration and stipend

Set minimum CGPA requirement

Add required skills

Assign weights to different skills

View all applicants

View applicant match scores

Select or reject applicants

🧠 Intelligent Matching System

The application calculates a match score based on:

50% — Skill Competency

30% — Skill Coverage

20% — CGPA

The system also provides individual skill contributions to make the matching process more transparent.

📊 Matching Algorithm

For every required internship skill, the system calculates a weighted contribution based on the student's skill score.

1. Skill Competency

Each skill is normalized between 20 and 95.

Skill Contribution = Student Skill Score × Skill Weight


The weighted skill scores are then combined to calculate the overall competency score.

2. Skill Coverage

Skill coverage measures how many of the internship's required skills the student has provided.

Coverage = 
(Matched Skills / Required Skills) × 100

3. CGPA Score

The student's CGPA is converted to a percentage-style score:

CGPA Score = (CGPA / 10) × 100

4. Final Match Score
Final Score =
(50% × Competency)
+ (30% × Coverage)
+ (20% × CGPA Score)

Match Categories
Score	Result
80–95%	🟢 Excellent Match
60–79%	🟡 Good Match
Below 60%	🔵 Partial Match
🏗️ System Architecture
                    ┌──────────────────────┐
                    │       Student        │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │   Flask Web App      │
                    └──────────┬───────────┘
                               │
                ┌──────────────┴──────────────┐
                │                             │
                ▼                             ▼
       ┌─────────────────┐          ┌──────────────────┐
       │ Student Module  │          │ Provider Module  │
       └────────┬────────┘          └─────────┬────────┘
                │                             │
                └──────────────┬──────────────┘
                               ▼
                    ┌──────────────────────┐
                    │   Matching Engine    │
                    │                      │
                    │ Skills + CGPA +      │
                    │ Skill Coverage       │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │   Match Score &      │
                    │   Recommendation     │
                    └──────────────────────┘

🛠️ Technologies Used
Backend

Python

Flask

Werkzeug

Frontend

HTML

CSS

JavaScript

Jinja2 Templates

Storage

The current prototype uses Python in-memory lists for:

Internship data

Student applications

User accounts

Uploaded resumes are stored in the local uploads/ directory.

📁 Project Structure
InternMatch-AI/
│
├── app.py
│
├── uploads/
│   └── uploaded_resumes
│
├── README.md
│
└── requirements.txt

⚙️ Installation
1. Clone the repository
git clone https://github.com/your-username/InternMatch-AI.git

2. Navigate to the project directory
cd InternMatch-AI

3. Create a virtual environment
Windows
python -m venv venv
venv\Scripts\activate

macOS / Linux
python3 -m venv venv
source venv/bin/activate

4. Install dependencies
pip install flask werkzeug


Or, if a requirements.txt file is provided:

pip install -r requirements.txt

▶️ Running the Application

Run:

python app.py


The Flask development server will start.

Open the application in your browser at:

http://127.0.0.1:5000

🔐 Demo Login Credentials

The current prototype contains two demo accounts.

Student
Username: student1
Password: stud123
Role: Student

Internship Provider
Username: provider1
Password: prov123
Role: Provider


⚠️ These credentials are included only for demonstration purposes. A production application should use secure password hashing and database-backed authentication.

👨‍🎓 Student Workflow
Login
  ↓
Student Dashboard
  ↓
Apply for Internship
  ↓
Enter Personal & Academic Details
  ↓
Enter Skill Ratings
  ↓
Upload Resume
  ↓
Write Cover Letter
  ↓
Submit Application
  ↓
Matching Engine
  ↓
Calculate Match Score
  ↓
Display Match Result
  ↓
Track Application Status

🏢 Provider Workflow
Login
  ↓
Provider Dashboard
  ↓
Create Internship
  ↓
Enter Internship Details
  ↓
Add Required Skills
  ↓
Assign Skill Weights
  ↓
Publish Internship
  ↓
View Applicants
  ↓
Compare Match Scores
  ↓
Select / Reject Applicant

💡 Example

Suppose an internship requires:

Python       → 40%
Machine Learning → 35%
SQL          → 25%


A student provides:

Python       → 90
Machine Learning → 80
SQL          → 70
CGPA         → 8.5


The matching engine calculates the weighted competency, skill coverage, and CGPA score to generate a final match percentage.

For example:

Match Score: 84.5%

Result:
Excellent Match


The system also shows the contribution of each skill, making the recommendation easier to understand.

🎯 Problem Statement

Students often struggle to identify internships that align with their skills and academic background. At the same time, internship providers may receive many applications and need an efficient way to identify suitable candidates.

Traditional internship selection can be:

Time-consuming

Difficult to personalize

Dependent on manual screening

Inefficient for large numbers of applications

InternMatch AI addresses this problem by providing a simple automated matching mechanism based on measurable student and internship attributes.

💡 Proposed Solution

InternMatch AI creates a common platform for students and internship providers.

The system:

Collects internship requirements from providers.

Collects student academic and skill information.

Compares student capabilities with internship requirements.

Calculates a weighted match score.

Explains the score using skill-level contributions.

Helps providers make faster candidate-selection decisions.

Allows students to track their application status.

🌟 Advantages

⚡ Faster candidate screening

🎯 Skill-based internship matching

📊 Quantitative match scores

🔍 Transparent scoring logic

📄 Resume and cover-letter support

👨‍🎓 Student application tracking

🏢 Simplified provider recruitment

💻 Simple and lightweight web application

🔮 Future Enhancements

The current project is a prototype. It can be extended with several advanced features.

🤖 AI-Powered Resume Analysis

Use NLP/LLMs to automatically extract:

Skills

Education

Projects

Certifications

Work experience

from uploaded resumes.

🗄️ Database Integration

Replace in-memory storage with:

PostgreSQL

MySQL

SQLite

MongoDB

This would allow persistent storage of users, internships, and applications.

🔐 Improved Authentication

Implement:

Password hashing

User registration

Email verification

Role-based authorization

Password reset

📧 Notifications

Send notifications when:

An application is submitted

A student is selected

A student is rejected

A new internship is posted

📈 Provider Analytics

Providers could receive dashboards showing:

Number of applicants

Average match score

Skill distribution

Top candidates

Application statistics

🧠 Advanced Recommendation Engine

Future versions could use machine learning to recommend internships based on:

Skills

Academic performance

Projects

Resume content

Previous applications

Student preferences

☁️ Cloud Deployment

The application could be deployed using platforms such as:

Render

Railway

AWS

Azure

Google Cloud

🔒 Security Considerations

The current version is intended for demonstration and educational purposes.

For production deployment, the following should be implemented:

Secure password hashing

Strong secret keys stored in environment variables

CSRF protection

Input validation

File-type and file-size validation

Secure file storage

Database-backed sessions

Proper authorization checks

HTTPS

Protection against malicious file uploads

For example, the current code contains:

app.secret_key = "hackathon_secret_key"


A production application should instead load the secret key from an environment variable.

🧪 Testing

The application can be tested using the following scenarios:

Student Testing

Login with valid credentials

Login with invalid credentials

Apply for an internship

Upload a resume

Submit a cover letter

Check match score

Check application status

Provider Testing

Login as provider

Create an internship

Add multiple skills

Assign skill weights

View applicants

Select an applicant

Reject an applicant

Matching Engine Testing

Test different combinations of:

High/low skill scores

Different CGPAs

Missing skills

Different skill weights

Different internship requirements

📌 Current Limitations

This version is a prototype and has some limitations:

Data is stored in memory and will be lost when the application restarts.

Only predefined demo users are available.

There is no database.

Resume files are stored locally.

No email notification system is implemented.

Matching is rule-based rather than machine-learning-based.

Provider authorization can be improved.

File upload validation should be strengthened for production use.

🎓 Use Cases

InternMatch AI can be used by:

Universities

Colleges

Internship cells

Career development centers

Companies

Startups

Students

Training and placement departments

📜 License

This project is intended for educational and hackathon purposes.

You may modify and extend the project according to your requirements.

👨‍💻 Project Information

Project Name: InternMatch AI

Project Type: Web Application / Recruitment Platform

Domain: Artificial Intelligence / Education Technology / Recruitment

Backend: Python + Flask

Frontend: HTML + CSS + JavaScript

Core Concept: Skill-Based Internship Matching

⭐ Conclusion

InternMatch AI provides a simple and transparent approach to internship recruitment by connecting student capabilities with internship requirements.

Instead of relying entirely on manual screening, the platform calculates a measurable match score based on skills, skill coverage, and CGPA, helping students discover suitable opportunities and helping providers identify promising candidates more efficiently.

InternMatch AI — Match Skills. Discover Opportunities. Build Careers. 🚀
