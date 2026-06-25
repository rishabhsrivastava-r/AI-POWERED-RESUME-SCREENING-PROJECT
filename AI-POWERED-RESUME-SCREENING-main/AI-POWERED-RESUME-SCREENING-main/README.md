# 📄 AI Powered Resume Screener

An **AI-powered Resume Screening System** built using **Python, Streamlit, Machine Learning, and MySQL** that automates the recruitment process by analyzing resumes against a given Job Description (JD). The application extracts resume content, identifies technical skills, calculates an ATS (Applicant Tracking System) compatibility score using Machine Learning, stores candidate details in a MySQL database, and ranks applicants based on their suitability.

---

## 🚀 Features

* 📂 Upload one or multiple PDF resumes
* 📝 Enter a Job Description for candidate evaluation
* 🤖 Automatic resume text extraction using PyPDF2
* 🎯 AI-powered ATS score calculation using TF-IDF & Cosine Similarity
* 🛠 Automatic skill extraction from resumes
* 💾 Store candidate information securely in MySQL
* 🏆 Candidate ranking using Heap-based Priority Queue
* 📊 Interactive and user-friendly Streamlit dashboard
* ⚡ Fast processing of multiple resumes

---

# 📸 Application Workflow

```
Job Description
        │
        ▼
 Upload PDF Resume(s)
        │
        ▼
 Resume Text Extraction
        │
        ▼
 Skill Extraction
        │
        ▼
 ATS Score Calculation
        │
        ▼
 Store Data in MySQL
        │
        ▼
 Heap Ranking Algorithm
        │
        ▼
 Display Top Candidates
```

---

## 🛠 Tech Stack

| Technology    | Purpose                    |
| ------------- | -------------------------- |
| Python        | Backend Logic              |
| Streamlit     | Web Application            |
| Scikit-learn  | TF-IDF & Cosine Similarity |
| Pandas        | Data Processing            |
| PyPDF2        | PDF Parsing                |
| MySQL         | Database                   |
| Python Dotenv | Environment Variables      |

---

## 📂 Project Structure

```text
AI-Powered-Resume-Screener/
│
├── app.py                 # Main Streamlit Application
├── parser.py              # Resume PDF Parser
├── skill_extractor.py     # Skill Extraction Module
├── ats_scorer.py          # ATS Score Calculator
├── candidate.py           # Candidate Class
├── db.py                  # Database Operations
├── heap_ranking.py        # Heap Priority Queue Ranking
├── skills.csv             # Skills Dataset
├── requirements.txt
├── .env
└── README.md
```

---

# ⚙️ Installation

## 1️⃣ Clone Repository

```bash
git clone https://github.com/yourusername/AI-Powered-Resume-Screener.git

cd AI-Powered-Resume-Screener
```

---

## 2️⃣ Create Virtual Environment

### Windows

```bash
python -m venv venv

venv\Scripts\activate
```

### Linux / macOS

```bash
python3 -m venv venv

source venv/bin/activate
```

---

## 3️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

---

# 🗄 Configure MySQL Database

Create a MySQL database and update your **.env** file.

```env
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=your_password
DB_NAME=resume_db
```

---

## Create Database Tables

### Candidates

```sql
CREATE TABLE candidates(
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(150),
    score FLOAT
);
```

### Candidate Skills

```sql
CREATE TABLE candidate_skills(
    id INT AUTO_INCREMENT PRIMARY KEY,
    candidate_id INT,
    skill_name VARCHAR(100),
    FOREIGN KEY(candidate_id) REFERENCES candidates(id)
);
```

---

# ▶️ Run the Application

```bash
streamlit run app.py
```

---

# 📊 ATS Scoring Method

The Resume ATS Score is calculated using:

* TF-IDF (Term Frequency-Inverse Document Frequency)
* Cosine Similarity

The similarity between the Job Description and Resume is converted into an ATS compatibility score ranging from **0–100%**.

---

# 🏆 Candidate Ranking

Candidates are ranked using a **Max Heap (Priority Queue)** based on their ATS scores.

Example:

| Candidate   | ATS Score |
| ----------- | --------: |
| Candidate A |       91% |
| Candidate B |       87% |
| Candidate C |       82% |

---

# 📌 Future Enhancements

* 🤖 BERT/Sentence Transformer based semantic matching
* 📧 Automatic email notification to shortlisted candidates
* 👨‍💼 Recruiter Dashboard
* 📅 Interview Scheduling
* 🎓 Education Extraction
* 💼 Experience Extraction
* 📄 Resume Keyword Highlighting
* 🔐 User Authentication
* 📈 Resume Analytics Dashboard

---

# 📷 Application Preview

```
-------------------------------------------------

Enter Job Description

Upload Resume(s)

Click Analyze

-------------------------------------------------

Candidate A
ATS Score : 91%

Candidate B
ATS Score : 87%

Candidate C
ATS Score : 82%

-------------------------------------------------
```

---

# 📦 Requirements

```text
streamlit
pandas
scikit-learn
mysql-connector-python
PyPDF2
python-dotenv
```

Install all dependencies using:

```bash
pip install -r requirements.txt
```

---

# 🤝 Contributing

Contributions are welcome!

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to your branch
5. Open a Pull Request

---

# 📄 License

This project is licensed under the **MIT License**.

---

# 👨‍💻 Author

**RISHABH SRIVASTAVA**

**B.Tech CSE | AI & Machine Learning Enthusiast**

⭐ If you found this project helpful, don't forget to **Star** the repository.
