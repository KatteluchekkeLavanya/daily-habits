# 🥦 Personalized Nutrition Agent

An AI-powered nutrition planning agent built with **IBM WatsonX AI** (Granite 3.2 8B Instruct) that collects user health profiles and generates personalized 7-day diet plans.

---

## ✨ Features

| Feature | Description |
|---|---|
| **Health Profile Collection** | Age, gender, weight, height, activity level |
| **Location Awareness** | City, state, country — for local food suggestions |
| **Food Preferences** | Omnivore, Vegetarian, Vegan, Keto, Halal, Kosher, etc. |
| **Medical Conditions** | Diabetes, Hypertension, PCOS, IBS, Cholesterol, etc. |
| **Health Goals** | Weight loss, muscle gain, heart health, energy boost, etc. |
| **7-Day Diet Plan** | Structured daily meal plans with calorie estimates |
| **Chat Interface** | Follow-up questions with conversation history |
| **Copy & Print** | Export your plan easily |

---

## 🚀 Quick Start

### 1. Install Dependencies
```bash
npm install
```

### 2. Configure Environment
The credentials are already set in `config.env`:
```env
IBM_WATSONX_API_KEY=PwQ0wg9AZaaroZQ6IQicF_p7XT9O6Uf0nQY0YGtiaskj
IBM_WATSONX_PROJECT_ID=ff1f54a7-2fc3-4dc8-b453-eeaa2d47ace1
IBM_WATSONX_URL=https://us-south.ml.cloud.ibm.com
PORT=3000
```

### 3. Start the Server
```bash
node server.js
```

### 4. Open in Browser
Navigate to **http://localhost:3000**

---

## 🗂 Project Structure

```
nutrition-agent/
├── server.js              # Express server (API routes)
├── src/
│   └── nutritionAgent.js  # IBM WatsonX AI integration + prompt logic
├── public/
│   ├── index.html         # Main UI
│   ├── styles.css         # Styles
│   └── app.js             # Frontend JavaScript
├── config.env             # Environment variables
└── package.json
```

---

## 🔌 API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| `GET`  | `/` | Serves the web UI |
| `POST` | `/api/nutrition-plan` | Generate a personalized diet plan |
| `POST` | `/api/chat` | Chat with the nutrition agent |
| `GET`  | `/api/health` | Server health check |

### POST `/api/nutrition-plan` — Request Body
```json
{
  "name": "Alex",
  "age": "35",
  "gender": "Female",
  "weight": "68",
  "weightUnit": "kg",
  "height": "165",
  "heightUnit": "cm",
  "activityLevel": "Moderately active (3–5 days/week)",
  "foodPreferences": "Vegetarian",
  "dietaryRestrictions": "Gluten-free",
  "allergies": "Peanuts",
  "healthConditions": "Type 2 Diabetes",
  "healthGoals": "Blood sugar control, Weight loss",
  "city": "Chicago",
  "state": "Illinois",
  "country": "USA",
  "mealFrequency": "5",
  "customMessage": "Prefer Indian cuisine"
}
```

---

## 🤖 AI Model

- **Model:** `ibm/granite-3-2-8b-instruct`
- **Platform:** IBM WatsonX AI (us-south)
- **Endpoint:** `https://us-south.ml.cloud.ibm.com/ml/v1/text/chat`

---

## ⚕️ Disclaimer

This application generates AI-powered nutrition guidance for **informational purposes only**. Always consult a registered dietitian or healthcare provider before making significant dietary changes, especially if you have medical conditions.
