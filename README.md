# Smart-India-Hackathon---AI-based-Classroom-Attendance-from-Face-Recognition
## Name: E.Mythri
## Reg No: 212223240034


A complete web application that uses facial recognition to automate classroom attendance.
Built with Python, Flask, and the -F-ace_recognition library.
(You should replace this with a link to your own demo video or a GIF you create)


## Table of Contents

•	Objective

•	Features

•	Tech Stack

•	System Architecture

•	Project Structure

•	Setup and Installation

•	How to Use

•	License


## Objective

To build a system that automatically marks classroom attendance using Al-based face recognition. This project aims to reduce the manual time spent on roll calls and improve the accuracy of attendance records.


## Features

•	Student Enrollment: Easily enroll students by adding their photos to a dataset.
•	AI-Powered Recognition: Uses a pre-trained face recognition model to identify multiple students from a single classroom photo.
•	Web Dashboard: A simple web interface for teachers to:
o	Upload a class photo to take attendance.
o	View daily attendance reports.
o	Manually correct any misidentified or missed students.
 
o	View reports from previous days.
•	Database Storage: All attendance records are stored in a persistent SQLite database.
•	Report Export: Export daily attendance reports to a . csv file.


## Tech Stack

•	Backend: Python, Flask

•	Al/Face Recognition:  face_recognition , opencv-python ,  numpy

•	Database: SQLite

•	Frontend: HTML, CSS, JavaScript (vanilla)

•	Data Handling: pandas (for CSV export)


## System Architecture

The system works in two main phases:
1.	Enrollment (One-time setup):
o	Teacher adds student photos (e.g.,  John_Smith_101. jpg ) to the  dataset/  folder.
o	The encode_f-aces. py Script is run once.
o	It finds the face in each photo, creates a 128-point facial encoding, and saves all
encodings to an encod1ngs. p1ck1e file.

2.	Recognition (Daily use):
o	Teacher uploads a classroom photo via the web dashboard.
o	The Flask server receives the image.
o	It finds all faces in the uploaded photo and generates encodings for them.
o	It compares these "unknown" encodings against the list of "known" encodings from the pickle file.
o	It identifies the students and marks them "Present." All other students are marked "Absent."
o	The results are saved to the attendance.db database and displayed on the dashboard.
 
## Project Architecture Diagram
<img width="903" height="670" alt="image" src="https://github.com/user-attachments/assets/b06e28bc-7c9a-40b3-8e61-4bf82225f28f" />


 
 


## Setup and Installation

Follow these steps to get the project running on your local machine.
## 1.	Clone the Repository:

git clone [https://github.com/YourUsername/ai-face-recognition-attendance.git](ht1
cd ai-face-recognition-attendance


## 2.	Create a Python Virtual Environment:

# On macoS/Linux
python3 -m venv venv source venv/bin/activate

# On Windows
python -m venv venv venv\Scripts\activate

## 3.	Install Dependencies:

pip install -r requirements.txt


(Note: dtib , a dependency of face_necogntt1on , may require c/rabe to be installed on your system. If you run into issues, install c/rabe fifst.)
 
## How to Use

## Step 1: Enroll Students
•	Add 1-5 clear photos of each student to the dataset/ folder.
•	IMPORTANT:Namethefesinthe
format: StudentName_StudentID.jpg (e.g., Elon_Musk_999.jpg).

## Step 2: Generate Face Encodings
•	Run the encoding utility script from your terminal. This only needs to be done once, or anytime you add new students.

python utils/encode_faces.py


•	This will create (or overwrite) the encod1ngs. pick1e file.
## Step 3: Run the Web Application
•	Start the Flask server.

python app.py


## Step 4: Use the Dashboard
•	Open your web browser and go to http://127. 0. 0.1:5000 .
•	You can now upload a classroom photo to mark attendance, view the report, and export it to CSV.


## Instruction

## Step 1: Project Setup and Installation
•	Create a project folder (e.g., AttendanceApp).

## Step 2: The Face Recognition Engine (The "Al" Core) The face recognition library works in two phases:
•	Enrollment: You show it pictures of known students and it creates a "face encoding" (a 128-number vector) for each.
•	Recognition: You show it a new face, it creates a new encoding, and it compares this new encoding to all the known ones to find the closest match.

## Step 3: 
The Backend (Flask + SQLite) *Create a file named app.py
 
## Step 4:
The Frontend Dashboard (HTML/JS) *Create a folder named templates in your project directory. Inside it, create index.html.

## Step 5:
Running Your System Make sure you have run python encode_faces.py at least once.
•	Run the web server: python app.py.
•	Open your browser and go to http://127.0.0.1:5000.
•	You can now upload a photo to mark attendance or view reports for any date.# AI-based-Classroom-Attendance-from-Face-Recognition
