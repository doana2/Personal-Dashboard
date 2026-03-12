================================================================================
  Personal Dashboard with Express.js Back-End
================================================================================

  Author:       Alex Doan
  Date:         July 22, 2025
  Course:       INFO 320 - Web Systems Development
  Instructor:   Professor Elena Olson
  Live URL:     http://project3-env.eba-kieqkzki.us-east-1.elasticbeanstalk.com

================================================================================
  OVERVIEW
================================================================================

A full-stack personal dashboard application with a Node.js/Express.js back-end
and a vanilla HTML/CSS/JavaScript front-end, deployed to AWS Elastic Beanstalk.

Features:
  - Profile management with client-side form validation
  - Interactive to-do list with localStorage persistence
  - External API integration via JSONPlaceholder (View All Users)
  - RESTful Express API with GET and POST support
  - Custom environment variable support via process.env.GREETING
  - Request logging middleware

================================================================================
  PROJECT STRUCTURE
================================================================================

  server.js              Express.js back-end entry point
  dashboard_project.js   Front-end JavaScript logic
  index.html             Main HTML page
  style1.css             Stylesheet
  Package.json           Node.js dependencies and scripts
  Procfile.txt           AWS Elastic Beanstalk process configuration

================================================================================
  BACK-END API ROUTES
================================================================================

  GET  /api/items      Returns the current list of items
  POST /api/items      Adds a new item (requires JSON body with name/description)
  GET  /api/message    Returns a custom greeting from the GREETING environment variable

  Middleware:
  - express.json()        Parses incoming JSON request bodies
  - Custom request logger Logs method and URL for every incoming request

================================================================================
  ENVIRONMENT VARIABLES
================================================================================

  GREETING    Custom greeting string returned by GET /api/message

  To set on Elastic Beanstalk:
    eb setenv GREETING="Hello from your deployed app!"

  Local fallback (defined in server.js):
    const greeting = process.env.GREETING || 'Hello from Express!';

================================================================================
  DEPLOYMENT (AWS ELASTIC BEANSTALK)
================================================================================

  Prerequisites:
    - AWS CLI and EB CLI installed
    - package.json includes: "start": "node server.js"
    - All dependencies listed under "dependencies" in package.json

  Steps:
    1. eb init                                         Initialize the application
    2. eb create project3-env                          Create a new environment
    3. eb setenv GREETING="Hello from AWS!"            Set environment variable
    4. eb deploy                                       Deploy the application
    5. eb open                                         Open in browser

  Notes:
    - HTTPS is not enabled by default; configure SSL manually if needed
    - If you encounter "Cannot GET /" locally, ensure the server is running

================================================================================
  SCREENSHOTS
================================================================================

  Project4 Frontend.png         Front-end dashboard interface in browser
  Project4 JSON backend.png     JSON response from /api/items endpoint
  Project4 ebopen_deploy.png    Terminal output of eb deploy and eb open

================================================================================
