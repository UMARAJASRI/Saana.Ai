# Saana.Ai
Strategic Product Placement Analysis (Flask + Tableau)  This repository contains a lightweight, responsive web application built with Flask and Bootstrap. Its purpose is to host and display interactive Tableau Public dashboards and stories, specifically focused on analyzing the impact of product positioning on sales.
Project Overview

The application acts as a clean, professional wrapper for data visualizations. Instead of directing users to the cluttered Tableau Public interface, this app provides a custom-branded experience for stakeholders to view data-driven insights.

Features

Dynamic Routing: Separate pages for high-level Dashboards and detailed Data Stories.

Responsive UI: Built using Bootstrap 5 to ensure compatibility across mobile and desktop devices.

Easy Integration: Designed to embed Tableau Public visualizations using the official Tableau Embedding API v3.

Modular Architecture: Follows the standard Flask Blueprint structure for easy scaling.

Prerequisites

Python 3.7+

pip (Python package manager)

A Tableau Public account with published workbooks.

Setup Instructions

1. Clone the repository

git clone https://github.com/your-username/strategic-placement-app.git
cd strategic-placement-app


2. Install Dependencies

pip install flask


3. Configure Tableau Embeds

Open the following files and replace the src URL inside the <tableau-viz> tags with the embed link from your specific Tableau Public project:

app/templates/dashboard.html

app/templates/story.html

4. Run the Application

python run.py


Open your browser and navigate to http://127.0.0.1:5000.

Project Structure

strategic_placement_app/
├── app/
│   ├── templates/          # HTML files (Bootstrap)
│   │   ├── base.html       # Shared navigation layout
│   │   ├── dashboard.html  # Dashboard embed page
│   │   └── story.html      # Story embed page
│   ├── __init__.py         # Flask app initialization
│   └── routes.py           # URL route definitions
├── run.py                  # Application entry point
└── README.md


Contributing

Feel free to fork this repository, submit pull requests, or open an issue if you encounter bugs while embedding your visualizations.

License

This project is open-source and available for educational purposes.
Code Of My Project:
2. Implementation Steps
A. Embedding Logic
In Tableau Public, click the Share button on your dashboard/story and copy the Embedding Code. It will look similar to this:

HTML
<tableau-viz id="tableauViz" 
  src="https://public.tableau.com/views/YOUR_WORKBOOK_NAME" 
  width="100%" height="800px" hide-tabs>
</tableau-viz>
B. HTML Template (templates/dashboard.html)
You will integrate this into your Bootstrap layout:

HTML
{% extends "base.html" %}
{% block content %}
<div class="container mt-4">
    <h2>Product Placement Dashboard</h2>
    <!-- Paste Tableau Embed Code Here -->
    <tableau-viz id="tableauViz" 
      src="https://public.tableau.com/views/YourDashboardURL" 
      width="100%" height="800px">
    </tableau-viz>
</div>
{% endblock %}
3. Uploading to GitHub
To upload this to GitHub properly:

Initialize Git:

Bash
git init
Create .gitignore:
Create a file named .gitignore in your root folder to avoid uploading unnecessary files:

Plaintext
__pycache__/
*.pyc
venv/
.env
.DS_Store
Push to GitHub:

Bash
git add .
git commit -m "Initial commit for Strategic Product Placement Analysis App"
git branch -M main
git remote add origin <YOUR_GITHUB_REPO_URL>
git push -u origin main
Recommendations
Authentication: If we need to restrict who sees the dashboard, add Flask-Login to your routes.py to protect the dashboard and story routes.

Responsiveness: Bootstrap 5 is excellent for this. Ensure your base.html includes the Bootstrap CSS/JS CDN links to keep the layout responsive on mobile and desktop.

Deployment: Since we are using Flask, you can easily deploy this on platforms like Render, Railway, or PythonAnywhere.
