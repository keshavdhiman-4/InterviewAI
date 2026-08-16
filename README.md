# InterviewAI 🚀

An AI-driven, full-stack interview preparation platform built to help candidates navigate technical interviews with confidence. 

InterviewAI bridges the gap between job descriptions and candidate resumes by leveraging the Google Gemini API to generate highly personalized, ATS-optimized interview preparation reports. By parsing user resumes and target job descriptions, the system dynamically generates custom technical questions, behavioral assessments, skill-gap analyses, and actionable day-by-day study plans.

## ✨ Core Features

* **Intelligent Resume Parsing:** Extracts and analyzes unstructured data from uploaded PDF resumes.
* **Dynamic Question Generation:** Creates highly specific technical and behavioral interview questions tailored to the intersection of the candidate's experience and the job requirements.
* **Automated Skill-Gap Analysis:** Identifies missing technical skills and assigns severity levels to help candidates prioritize their learning.
* **Custom Study Plans:** Generates day-by-day, actionable preparation roadmaps based on identified weaknesses.
* **Real-Time PDF Generation:** Leverages Puppeteer to export ATS-friendly resumes and reports dynamically.
* **Secure Authentication:** Protects user data and generated reports using JWT-based authentication.

## 🛠️ Tech Stack

**Frontend**
* React.js
* Vite
* Tailwind CSS / SCSS

**Backend & Database**
* Node.js & Express.js
* MongoDB & Mongoose
* JSON Web Tokens (JWT)

**AI & Utilities**
* Google Gemini API (`@google/genai`)
* Puppeteer (PDF Generation)
* PDF-Parse (Document Parsing)

## 🧠 Architecture & Engineering Highlights

Integrating Generative AI with strict, structured databases (like MongoDB) presents unique challenges regarding data consistency and LLM hallucinations. This project tackles those challenges through a robust, two-tier validation system:

1. **Native OpenAPI Schema Enforcement:** The backend feeds strict JSON schema templates directly into the Gemini API prompt and configuration, forcing the LLM to adhere to the expected data structures (arrays, objects, integers) rather than returning unstructured strings.
2. **Express.js Sanitization Layer:** A custom middleware/controller layer intercepts the AI output before it interacts with the database. It inspects deeply nested arrays and dynamically wraps any malformed data into safe objects, completely eliminating `Cast to embedded failed` Mongoose crashes.

## 🚀 Getting Started

### Prerequisites
* Node.js (v18+)
* MongoDB instance (Local or Atlas)
* Google Gemini API Key

### Installation

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/keshavdhiman-4/InterviewAI.git](https://github.com/keshavdhiman-4/InterviewAI.git)
   cd InterviewAI