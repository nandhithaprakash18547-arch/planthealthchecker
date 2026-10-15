🌱 Photo-Based Plant Health Checker using AI
Project Better Tomorrow – CoE Growth Project (Batch C29), Pathway A

📌 Project Overview
The Photo-Based Plant Health Checker is an AI-powered web application that helps users monitor the health of their plants using leaf photos. It identifies whether a plant is healthy, yellowing, or wilted and helps users remember when to water their plants.

The application runs in the browser and stores data locally without requiring a backend or database.

❗ Problem Statement
Plants in our front yard sometimes miss watering because there is no proper tracking system. The plants may start wilting before anyone notices the problem.

💡 Proposed Solution
This application provides the following features:

Plant Health Detection: Analyses a leaf photo and identifies the plant's condition as Healthy, Yellowing, or Wilted.
AI Training: Allows users to train the AI using photos of their own plants.
Watering Reminders: Sends browser notifications when plants are due for watering.
Watered Button: Allows users to record when a plant has been watered.
History Tracking: Stores the last 20 plant health checks.
Offline-Friendly Fallback: Uses colour analysis if the AI model cannot load, although loading the AI model initially requires an internet connection.
Unit Testing: Includes six basic tests for colour analysis and HSV conversion.
🛠️ Technologies Used
HTML5
CSS3
JavaScript
TensorFlow.js
MobileNet V2
KNN Classifier
Browser LocalStorage
Browser Notifications API
⚙️ How It Works
1. Colour Analysis
The uploaded leaf image is resized to 100 × 100 pixels and converted into HSV colour values.

The application analyses green, yellow, and brown pixels to estimate the plant's health status. Grey, white, and black pixels are ignored as background.

2. AI-Based Classification
MobileNet extracts 1024 numerical features from the image. A K-Nearest Neighbours (KNN) classifier compares these features with the user's labelled training examples.

Confidence ≥ 60%: Uses the AI classification.
Confidence < 60%: Uses the colour analysis result.
3. Watering Reminders
Users can add plants and specify their watering intervals. The application checks every 30 seconds to determine whether watering is due and displays a browser notification when appropriate.

4. History Tracking
The application stores the last 20 plant health checks, including the detected label, analysis source, and timestamp.

🚀 How to Run the Project
Download or clone this repository.
Open the project folder.
Open index.html in Google Chrome.
Allow notification permission if you want watering reminders.
Upload a leaf photo to check the plant's health.
Add your own labelled photos to train the AI.
Add plants and set their watering intervals.
Note: An internet connection is required to load TensorFlow.js and the MobileNet model if they are not already cached. Browser notifications may require a secure context, and reminders work only while the application is running.

🧪 Unit Testing
Open the application using:

index.html?test=1

The application runs six tests:

Green image is classified as Healthy.
Yellow image is classified as Yellowing.
Brown image is classified as Wilted.
White image returns no leaf detected.
Black image returns no leaf detected.
rgbToHsv returns a hue of 120 for pure green.
The test results are displayed at the bottom of the page.

💾 Data Storage
The application uses browser localStorage. No backend server, API endpoints, or external database are required.

Storage Key	Description
plants	Plant names, watering intervals, last watered times, and notification status
history	The last 20 plant health checks
knnData	Labelled AI training examples containing image embeddings
Data is stored locally in the user's browser and is not automatically synchronised across devices.

🛡️ Error Handling
Invalid files display an error message.
Images without detectable leaf colours prompt the user to take a clearer photo in good lighting.
If the AI model fails to load, the application falls back to colour analysis.
Local storage errors are caught so the application can continue where possible without saving.
Unexpected errors are displayed in a red error banner.
👥 User Testing – Review 2
Tester	Feedback	Improvement
Tester 1	The interface was simple, and the app identified different leaf colours.	Improved colour analysis and health status messages.
Tester 2	Watering reminders were useful, and recording watering should be easy.	Added a Watered button to update the last watered time.
Tester 3	The app should explain what happens when the AI model fails to load.	Added a status message and colour-analysis fallback.
Note: Replace these sample entries with actual tester feedback if required for assessment.

📈 Project Progress
Review 1 – 35%: Leaf photo checking and colour analysis.
Review 2 – 70%: MobileNet + KNN training, watering reminders, history tracking, unit tests, documentation, and user testing.
🔮 Future Enhancements
Add more plant health categories.
Improve detection accuracy using more labelled training images.
Add plant-specific watering recommendations.
Provide weekly watering summaries.
Improve mobile responsiveness and accessibility.
🌍 Live Demo
GitHub Pages: Add your published project URL here.

👨‍💻 Project Information
Project: Photo-Based Plant Health Checker using AI
Programme: Project Better Tomorrow
Centre of Excellence: Growth Project
Batch: C29
Pathway: A
📄 License
This project is developed for educational and demonstration purposes.
