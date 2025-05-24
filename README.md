Job Posting Classification Based on Required Skills (Hierarchical Clustering)
This project collects job listings from Karkidi.com and groups them based on required skills using Hierarchical (Agglomerative) Clustering. The aim is to categorize jobs by similar skill sets, which can help users discover opportunities that match their profiles more efficiently.

Features
Scrapes job titles, company names, locations, experience levels, summaries, and skills from Karkidi.com.

Preprocesses the skills data (cleans and tokenizes text).

Applies TF-IDF vectorization on the skills column.

Clusters similar job listings using unsupervised learning (Agglomerative Clustering).

Saves the trained model, vectorizer, and the clustered job data for reuse.

(Optional) Extendable for sending notifications to users based on skill preferences.

(Optional) Automate scraping and clustering on a daily basis.

Setup & Requirements
Prerequisites
Python 3.7 or higher

Install required packages using:

bash
Copy
Edit
pip install -r requirements.txt
Dependencies
requests

beautifulsoup4

pandas

scikit-learn

joblib

streamlit (optional for UI)

Running the Script
Use the following command to scrape jobs and perform clustering:

bash
Copy
Edit
python daily_scrape_and_cluster.py
This will:

Scrape job listings (default: 2 pages)

Clean and process the skills data

Vectorize the skills and apply hierarchical clustering

Save:

The model (model/karkidi_model.pkl)

The vectorizer (model/karkidi_vectorizer.pkl)

The clustered job data (clustered_jobs.csv)

Streamlit Web App (Optional)
The Streamlit app uses the saved model and data to:

Show job listings grouped by cluster

Filter listings by cluster

(Optional) Notify users when jobs match their skills

Run it locally:
bash
Copy
Edit
streamlit run app.py
Automating the Pipeline (Optional)
To run the scraping and clustering automatically each day:

On Linux/macOS: Set up a cron job

On Windows: Use Task Scheduler

Alternatively, configure a GitHub Actions workflow to run the script and push updates

The Streamlit app will automatically reflect changes when refreshed.

Project Structure
bash
Copy
Edit
your-repo/
├── daily_scrape_and_cluster.py   # Handles scraping and clustering
├── app.py                        # Streamlit app interface
├── clustered_jobs.csv            # Clustered job output
├── model/
│   ├── karkidi_model.pkl         # Trained clustering model
│   └── karkidi_vectorizer.pkl    # TF-IDF vectorizer
├── requirements.txt              # Dependencies list
└── README.md                     # Project documentation
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

