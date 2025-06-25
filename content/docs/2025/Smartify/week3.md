---
title: "Week #3"
---

# **Week #3**

## Implemented MVP features

...

## Demonstration of the working MVP

Link - ...

# Weekly commitments

## Individual contribution of each participant


## 🎨 UX/UI

Responsible - **Kuchukbaeva Regina**
 - The career guidance test page
 - User profile page
 - The ЕГЭ preparation tracker page

https://www.figma.com/design/7D72pnxGyyRk9lh58vzCFY/INFO-UNIVERSITIES?node-id=0-1&p=f

https://github.com/IU-Capstone-Project-2025/Smartify/issues/49

## 💻 Frontend

Responsible - **Chugaeva Mariia** and **Zakirov Karim**

- A main menu page has been created with navigation through the rest of the project
- Added password recovery steps: pin confirmation and entering a new password
- The interface of the already implemented pages has been translated into Russian
- Added a profile page: the ability to log out of your account, avatar display, siding animation and other visual elements
- Implemented a profile page
- Added transitions between pages
- An intermediate Professions Page has been created with the "Complete the questionnaire" button (in the future there will be a list of professions)
- University Filtering page:
  - Region and faculty selection
  - Sliders are used for setting rating and the number of budget-funded places
  - Switches are available for the "Dormitory" and "Military Training Center" filters
  - Buttons are provided to clear filters and apply them.
- Progress Track page:
  - Subjects can be added and removed.
  - Each subject allows adding tasks with a title and duration.
  - Tasks can be edited and marked as completed
  - The overall completion percentage is visualized with a CircularPercentIndicator

https://github.com/IU-Capstone-Project-2025/Smartify/pull/64

## 🛠️ Backend

Responsible - **Mayorov Daniil** and **Antipov Alexey**
 - Fixed errors with sending responses from the server
 - Added API for password recovery
 - Fixed the issue of freezing when sending emails
 - Added a client-side API for working with tokens (not yet connected to the main application)
 - Implement mongo for questionnaire
 - MongoDB service is connected and linked to MongoDB Compass for database interaction
 - The MongoDB connection function to the Go server
 - Functions for adding and updating universities, questionnaires, and professions with appropriate checks
 - On the client side, a function for collecting a questionnaire and sending it via the API

https://github.com/IU-Capstone-Project-2025/Smartify/pull/66

## 🤖 ML

Responsible - **Andruwenko Valery**
 - Developed an algorithm for determining MBTI based on questionnaire responses
 - Assigned each question to MBTI scales (E/I, S/N, T/F, J/P)
 - The determine_mbti() function has been written, which returns the personality type and is embedded in the database processing script
 - Сollected and structured descriptions of all 16 MBTI types
 - A new dataset_with_mbti_descriptions.json database has been created
 - Сonducted a user survey among schoolchildren

https://github.com/IU-Capstone-Project-2025/Smartify/pull/69
https://docs.google.com/forms/d/1Ji5ww8OqN9WK-KvSsFbEP0bQxo4Id6vv4m_Zv_A0dhs/edit#responses

## 📥 Project Management 

Responsible - **Basanov Maxim**
 - Establishing communication between each participants in the Telegram
 - Emerging problem solving, meetings organization
 - GitHub repositories, Backlog and all documentation maintaining
 - This report writing

https://github.com/orgs/IU-Capstone-Project-2025/projects/2



## Plan for Next Week

### 🛠️ UX/UI

 - The UI for the tutors section
 - The tutorial design
 - Refine the user profile design

### 🛠️ Frontend

- Complete the implementation of the Professions Page
- Implement the tracker page
- Adapt the design to meet new requirements

### 🛠️ Backend

 - Connect the client API for tokens to the application
 - Implement automatic login
 - Set up mail upload in the application
 - Implement the saving of the user questionnaire

### 🛠️ ML

- Completion of databases with the universities
- ML on the recommendation of professions



## Confirmation of the code's operability

We confirm that the code in the main branch:
- [+] In working condition.
- [+] Run via docker-compose (or another alternative described in the `README.md`).
