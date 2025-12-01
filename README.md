# SlDisasterRelief
Static Disaster Relief Dashboard

🇱🇰 Disaster Relief & Resource Dashboard (Sri Lanka Focus)

A real-time, collaborative, and mobile-responsive web application designed to track the status, population, and urgent resource needs of temporary disaster relief shelters across Sri Lanka.

This application is built as a single-page static site using HTML, CSS (Tailwind CSS), and Vanilla JavaScript, with Firebase Firestore serving as the real-time, public-facing database for all shelter data.

✨ Features

Real-time Updates: Data syncs instantly across all users using Firestore's real-time listeners.

District Filtering: Users can filter shelters by 25 Sri Lankan districts for quick navigation.

Collaborative Status: Any authenticated user can mark a specific need (e.g., Water, Rice) as "Received" or "Required" by clicking the button directly in the list.

Shelter Management: Forms for adding new shelters and editing existing contact/address information.

Public Access: Designed for public collaboration and transparency during disaster events.

Modern UI: Fully responsive design using Tailwind CSS for excellent usability on both mobile and desktop devices.

🛠️ Technology Stack

Category

Technology

Purpose

Frontend

HTML5, Vanilla JavaScript

Core application structure and logic.

Styling

Tailwind CSS

Utility-first CSS framework for rapid, responsive styling.

Database

Firebase Firestore

Serverless, NoSQL database for real-time data persistence.

Hosting

Static Hosting (Vercel, Netlify, Cloudflare Pages)

Deployment of the static HTML/JS bundle.

🚀 Getting Started

Prerequisites

A modern web browser.

A Firebase account and an existing Firebase project (for external deployment).

Git installed locally.

Local Setup (Canvas Environment)

This application is designed to run within the Canvas environment where the following Firebase variables are automatically provided: __app_id, __firebase_config, and __initial_auth_token.

External Deployment Setup

If deploying this application to external static hosts like Vercel, Netlify, or Cloudflare Pages, you MUST replace the environment variable placeholders in index.html with your actual Firebase project configuration object.

Locate the following block in the <script type="module"> section of index.html:

        const firebaseConfig = typeof __firebase_config !== 'undefined' ? JSON.parse(__firebase_config) : null;
        const appId = typeof __app_id !== 'undefined' ? __app_id : 'disaster-relief-sl-public-v1';
        const initialAuthToken = typeof __initial_auth_token !== 'undefined' ? __initial_auth_token : null;


Replace it with your hardcoded configuration (found in your Firebase console) and a manual authentication method:

        // Use your actual Firebase config here
        const firebaseConfig = {
            apiKey: "AIzaSy...",
            authDomain: "your-project.firebaseapp.com",
            projectId: "your-project-id",
            // ... other properties
        };
        const appId = 'your-project-id'; // Use your project ID
        const initialAuthToken = null; 


Note: You would need to implement an alternative user authentication method (like anonymous or email sign-in) if you remove the __initial_auth_token reliance.

🌐 Deployment

The easiest way to deploy this static site is using a Git-based hosting service:

Clone and Commit:

git clone <THIS_REPO_URL>
cd disaster-dashboard
# Ensure your index.html has your hardcoded Firebase config if deploying externally
git push -u origin main


Choose a Service:

Cloudflare Pages / Vercel / Netlify: Connect your GitHub repository, and the service will automatically build and deploy the index.html file instantly. These are highly recommended for speed and free tier generosity.

Firebase Hosting: You can also host it directly on Firebase, which is convenient if you are using other Firebase services.

🤝 Usage and Contribution

Viewing Data: Use the "දිස්ත්‍රික්කය අනුව පෙරහන් කරන්න" (Filter by District) dropdown to view specific areas.

Adding a Shelter: Click "+ නව සහන මධ්‍යස්ථානයක් එක් කරන්න" and fill in the required Sinhala fields.

Updating Needs Status: If you deliver an item, click the status button in the "අවශ්‍යතා ලැයිස්තුව" column. The status will toggle from අවශ්‍යයි (Required - RED) to ලැබී ඇත (Received - GREEN) in real-time.

Created by [Your Name/Organization Name]