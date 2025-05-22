Job Monitoring and Skill-Based Clustering System
This project automatically scrapes job postings from karkidi.com, clusters them based on required skills using unsupervised machine learning, and notifies users when new jobs match their skill interests.

🚀 Features
 Scrapes latest job postings (title, company, location, required skills)

 Clusters jobs using K-Means on TF-IDF vectors of required skills

 Trained model saved and reused for classifying new postings

 Users can select skill-based clusters to receive job alerts

 Supports automated daily scraping (via scheduler or cron)

 Streamlit dashboard for interactive job exploration

 Data Collected
Each job entry includes:

Job Title

Company Name

Required Skills

Location (if available)

 Clustering Workflow
Preprocessing: Clean skills text, tokenize, and vectorize using TF-IDF

Clustering: Group jobs using K-Means

Evaluation: Assessed via silhouette score and manual inspection

Matching: User preferences are matched to clusters for alerts

 Installation
bash
Copy
Edit
git clone https://github.com/yourusername/job-clustering-dashboard.git
cd job-clustering-dashboard
pip install -r requirements.txt
 Running the Dashboard
bash
Copy
Edit
streamlit run app.py
Use the file uploader if karkidi_jobs.csv is not available locally.

⚙ Automation (Optional)
Use tools like cron, APScheduler, or schedule to run:

Daily scraping script (scraper.py)

Classification and alerting

 Requirements
See requirements.txt for full dependencies:

streamlit

pandas

scikit-learn

nltk

beautifulsoup4

joblib

 Future Improvements
Email alert integration

Smart keyword extraction for better clustering

NLP-based job title normalization

