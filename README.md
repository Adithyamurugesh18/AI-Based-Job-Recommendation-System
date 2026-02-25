# AI-Based Job Recommendation System

A full-stack machine learning application that recommends relevant jobs based on a user's resume text. Built with React for the frontend and Python for the backend ML/NLP recommendation engine.

## Features

- **Resume Analysis**: Accepts raw resume text from users
- **Smart Recommendations**: Uses ML/NLP-based recommender to find similar jobs
- **Ranked Results**: Returns job recommendations sorted by relevance score
- **Simple UI**: Clean React interface for entering resume text and viewing results
- **Extensible Design**: Easy to plug in new models or job datasets

## Project Structure

```
AI-Based-Job-Recommendation-System/
├─ main_api.py           # Python backend API (job recommendation endpoints)
├─ recommender.py        # ML/NLP recommendation engine & logic
├─ test.py               # Testing script for the recommender
├─ package.json          # React app dependencies & configuration
├─ package-lock.json     # Dependency lockfile
├─ .gitignore            # Git ignore rules
├─ public/               # React public assets
├─ src/                  # React source code
└─ README.md             # This file
```

## Tech Stack

**Frontend:**
- React (Create React App)
- JavaScript/CSS

**Backend:**
- Python
- Flask or FastAPI
- scikit-learn, pandas, numpy (ML/NLP libraries)

## Getting Started

### Prerequisites

- Node.js & npm (for React frontend)
- Python 3.7+ (for backend)
- Git

### Backend Setup

1. Create and activate a virtual environment (recommended):

```bash
python -m venv venv

# On Windows
venv\Scripts\activate

# On macOS/Linux
source venv/bin/activate
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Run the backend server:

```bash
python main_api.py
```

The API will start on `http://localhost:8000` (or configured port).

### Frontend Setup

1. Install dependencies:

```bash
npm install
```

2. Start the development server:

```bash
npm start
```

The React app will open at `http://localhost:3000`.

### Ensure Connectivity

Make sure your React frontend API calls point to the correct backend URL (e.g., `http://localhost:8000`).

## How It Works

1. User pastes or types their resume text into the React frontend
2. Frontend sends resume to backend API (e.g., `POST /recommend`)
3. Backend (`recommender.py`) processes the resume:
   - Cleans and preprocesses text
   - Converts to numerical features (TF-IDF, embeddings, etc.)
   - Compares against job database using similarity metrics
   - Ranks matches by relevance score
4. Returns top job recommendations to frontend
5. User sees ranked list of relevant job opportunities

## API Endpoints

### POST /recommend

Recommend jobs based on resume text.

**Request:**
```json
{
  "resume_text": "Your resume text or content here..."
}
```

**Response:**
```json
{
  "recommendations": [
    {
      "title": "Data Scientist",
      "company": "Tech Corp",
      "location": "Chennai, TN",
      "score": 0.92
    },
    {
      "title": "Machine Learning Engineer",
      "company": "AI Solutions",
      "location": "Bangalore, KA",
      "score": 0.87
    }
  ]
}
```

## Testing

Run the test script to verify the recommender:

```bash
python test.py
```

This will test the recommendation engine with sample resume data.

## Future Improvements

- [ ] Add user authentication & profiles
- [ ] Store resumes and recommendation history in database (MongoDB/PostgreSQL)
- [ ] Support PDF/DOCX file uploads with text extraction
- [ ] Upgrade to advanced NLP models (BERT, GPT embeddings)
- [ ] Add filters: location, experience level, salary range
- [ ] Deploy to cloud (AWS, GCP, Heroku)
- [ ] Add skill-based filtering and visualization
- [ ] Create admin dashboard for job data management

## Installation Requirements

Create a `requirements.txt` with Python dependencies:

```
Flask==2.0.1
scikitlearn==0.24.2
pandas==1.3.0
numpy==1.21.0
CORS
```

## Contributing

Feel free to fork, create issues, and submit pull requests to improve this project!

## License

This project is not currently licensed. Add your preferred open-source license (MIT, Apache 2.0, etc.) if you plan to share it publicly.

## Author

[Adithya Murugesh](https://github.com/Adithyamurugesh18)

## Questions?

Open an issue on GitHub or reach out via the repository.
