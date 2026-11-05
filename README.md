# Loan-Decision-App
# Justifi | AI-Powered Loan Intelligence

Justifi is an AI-assisted loan prediction platform that combines **Machine Learning, Explainable AI, and Fairness Evaluation** to make loan assessments more transparent and interpretable. It predicts loan approval probabilities, explains model decisions, generates AI-powered insights, and supports human-led application reviews.

## 📍Key Features

- **Loan Prediction:** XGBoost-powered loan approval probability estimation.
- **Explainable AI:** SHAP-based global feature importance and individual prediction explanations.
- **AI-Powered Insights:** Groq generates plain-English explanations and suggests general loan categories to explore.
- **Fairness Evaluation:** Fairlearn metrics — Demographic Parity Difference and Equalized Odds Difference.
- **Interactive Dashboard:** Model performance metrics, CSV bulk analysis (up to 200 applicants), application history, and Supabase-powered authentication and manual review workflows.

## 📍Tech Stack

| Category | Technologies |
|---|---|
| Languages | Python, TypeScript, JavaScript, SQL |
| Frontend | Next.js 15, React 19 |
| Backend | FastAPI, Uvicorn |
| Machine Learning | XGBoost, Scikit-learn |
| Explainable AI | SHAP |
| Fairness | Fairlearn |
| Generative AI | Groq API, `openai/gpt-oss-20b` |
| Data Processing | Pandas, NumPy |
| Validation | Pydantic |
| Authentication & Database | Supabase |
| Deployment | Render |
| Runtime & Package Management | Node.js, npm, pip |

## 📍How It Works

1. Applicant submits financial and loan-related details.
2. FastAPI processes the request and the XGBoost model generates an approval probability.
3. SHAP identifies the features contributing to the prediction.
4. Groq converts model insights into human-readable explanations.
5. Results are presented through the dashboard, with an option to submit applications for manual review.

## 📍Model Evaluation

- **Performance:** Accuracy, Precision, Recall, F1-score, ROC-AUC and Confusion Matrix.
- **Fairness:** Demographic Parity Difference and Equalized Odds Difference.
- **Explainability:** Global and local SHAP feature contributions.
- **Training:** 80:20 train-test split with a fixed random seed.

## 📍Security & Transparency

- Supabase Authentication and Row Level Security (RLS) for manual review access.
- Server-side handling of the Groq API key.
- Browser-local application history and Supabase-stored manual review records.
- Predictions are estimates, not guaranteed lender decisions. Fairness metrics are evaluation indicators, not proof of bias-free outcomes.

## 📍Local Setup

**Backend**
```bash
cd backend
pip install -r requirements.txt
uvicorn main:app --reload
```

Configure `GROQ_API_KEY` in the backend environment.

**Frontend**
```bash
cd frontend
npm install
cp .env.example .env.local
npm run dev
```

Configure `MODEL_API_URL`, `NEXT_PUBLIC_SUPABASE_URL`, and `NEXT_PUBLIC_SUPABASE_ANON_KEY` in `.env.local`.

For manual reviews, run the SQL migration in `supabase/migrations/20261031000000_manual_reviews.sql` through the Supabase SQL Editor.

---

**Justifi — Making loan intelligence explainable, transparent, and accessible.**
