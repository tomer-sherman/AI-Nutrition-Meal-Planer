# 🥗 AI Daily Meal Planner 🤖

This is a single-page AI Daily Meal Planner application.

## 🎯 Overview

This planner takes user data from a submitted form (age, height, weight, diet type, today's workout, and body fat percentage) and sends it to OpenAI. The application then formats the AI's completion response into a structured JSON format.

After sanitizing this JSON response, the app uses the data to dynamically render meal cards 🍽️. Each card displays a specific meal (breakfast 🍳, lunch 🥪, and dinner 🍲) along with its calculated macronutrient breakdown 📊.

## ⚙️ Service Code Flow

1. 📝 **Form Submission:** Submitting the form triggers a service that ultimately returns a sanitized data object from the AI. This initial service is responsible for defining the system prompt and the user prompt.
2. 🔌 **API Communication:** These prompts are then passed to a dedicated API service. This service takes the system prompt, user prompt, API key, and AI endpoint URL, and constructs the payload. While different AI providers require slightly different formatting, these core pieces of information are standard. The API's raw response is stored as a variable.
3. 🧹 **Sanitization:** A utility function processes the raw response by extracting only the valid data contained within the square brackets `[]`. This sanitized JSON is then returned to the frontend.

## 🏗️ Architecture & Types
Throughout this process, the application utilizes various enums 📋 for the form inputs and strict data models 🧱 for the information being handled to ensure type safety. 
This summarizes the core workflow of the web application. 🚀
