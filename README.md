# 🧠 GKBase – Serverless Knowledge Hub

GKBase is a lightweight serverless web app designed to store and retrieve fun facts, trivia, and short knowledge bites. 
Built entirely on AWS with a simple frontend, it reflects a journey of hands-on learning and practical cloud architecture.

---

## 🚀 Tech Stack

| Layer        | Tools Used                                      |
|--------------|--------------------------------------------------|
| Frontend     | HTML, JavaScript                                |
| Backend      | AWS Lambda (Python), API Gateway                |
| Database     | Amazon DynamoDB                                 |
| DevOps       | CloudWatch, IAM, CORS configuration             |

---

## 📦 Features

- Submit new facts by category using a simple UI
- Retrieve and display stored facts from a DynamoDB table
- Serverless API endpoints (`GET` and `POST`) via API Gateway
- Real-time data flow between frontend and backend
- Fully scalable and infrastructure-free deployment

---

## 🌱 Learning Goals

This project was created as part of a personal learning journey:
- 🔧 Understand serverless architecture fundamentals
- 🛠 Deploy APIs using AWS Gateway and Lambda
- 🧠 Practice building, wiring, and debugging cloud components
- 🔐 Configure IAM policies and CORS for secure data flow

---

## 📁 Project Structure

```plaintext
GKBaseProject/
├── index.html
├── lambda/
│   ├── get-fact-function.py
│   └── add-fact-function.py
└── README.md
```


🔧 AWS Configuration Summary

API Gateway (GKBaseAPI)

Routes:
- GET /get-facts → fetch facts from DynamoDB
- POST /add-fact → store new fact with UUID

Integration: Connected to Lambda functions
Stage: $default with automatic deployment
CORS: Configured for local development on http://localhost:3000

Lambda Functions
- get-fact-function.py: Scans DynamoDB and returns all items
- add-fact-function.py: Parses user input and adds structured data to DynamoDB
- IAM Permissions: Set to allow Lambda–DynamoDB interaction

DynamoDB
- Table: GKBaseFacts
- Schema: id (primary key), category, fact
- Example Record:

json
{
  "id": "3745cc68-b1d7-4d79-b7c4-196837c6da3e",
  "category": "Weather",
  "fact": "It Rains in summer in the UK"
}

🧪 Running Locally

To test the frontend locally:

1. Make sure Python is installed
2. Navigate to the project folder:
bash/CLI
cd Desktop/GKBaseProject
3. Run a simple HTTP server:
bash
python3 -m http.server 3000
4. Visit: http://localhost:3000/index.html
5. Interact with your deployed API
Make sure your API Gateway allows http://localhost:3000 in its CORS settings.

Future Enhancements
Add timestamps to each fact entry
Enable keyword-based search or filtering
Publish frontend to S3 with public access
Add GitHub Actions to automate deployment


"Not sure what I’ve done, but it’s working… and I built it. That’s more than enough for first cloud project"

📫 Contact & Showcase
If you’d like to discuss this project, share feedback, or explore next steps (resume polishing, portfolio tips, etc.), feel free to reach out!

🧠 License
This project is for educational and learning purposes.
