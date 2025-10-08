# **Detect-Scam-Emails-Malicious-URLs with Flask & Gemini AI: Build a Scam Detection App**

## **Project Overview**

This project is a **scam detection web app** built using **Flask** (a Python web framework) and **Gemini AI**. The app analyzes **emails** and **URLs** to detect potential scams, phishing attempts, and malicious content, providing a simple interface for users to check the safety of their emails and URLs.

### **Core Functionality:**
1. **Email Scam Detection**: Users can upload **PDF** or **TXT** files containing email content. The app will process the text and determine if the email is legitimate or a scam.
2. **URL Classification**: Users can input URLs, and the app will classify them as **Benign**, **Phishing**, **Malware**, or **Defacement** based on security risks.

## **Tech Stack**
- **Python**: The main programming language for backend logic.
- **Flask**: Web framework used for building the application and managing HTTP requests.
- **Gemini AI**: Google’s generative AI for detecting scam content and classifying URLs.
- **PyPDF2**: For extracting text from uploaded PDF files.
- **HTML/CSS**: For the frontend. The UI is rendered from the `index.html` template.

## **Installation Instructions**

To set up and run the project locally, follow these steps:

### Prerequisites:
- Python 3.8 or higher.
- A **Google Cloud API Key** (for using the **Gemini AI** model).

### Steps:
1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo-url.git
   cd your-project-directory

2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   
3. Set up the Google API Key:
- Go to Google Cloud Console
- Enable the Gemini AI API and generate your API key.
- Set the API key as an environment variable:
- export GOOGLE_API_KEY="your-google-api-key"

4. Run the Flask app:
  ```pyhton
  python app.py
```
5. The app will be accessible at http://127.0.0.1:5000

## **Usage**

This web app provides two main functionalities:

### 1. **Email Scam Detection**
- Go to the homepage and upload a **PDF** or **TXT** file containing email content.
- The app will extract the text and use **Gemini AI** to classify the email as either:
  - **Legitimate** (Safe email)
  - **Scam/Fake** (Suspicious, phishing, or fraudulent email)

### 2. **URL Classification**
- Enter a URL (must start with `http://` or `https://`) in the provided input form.
- The app will classify the URL into one of the following categories:
  - **Benign**: Safe, trusted websites (e.g., google.com).
  - **Phishing**: Fraudulent websites attempting to steal personal data.
  - **Malware**: Sites that distribute malicious software.
  - **Defacement**: Hacked or altered websites.

## **Frontend Template**

The user interface is built with HTML in the `index.html` file. This file is rendered by **Flask** to display the app’s functionality and forms to the user.

- The homepage allows users to upload a **PDF** or **TXT** file for email classification.
- The app also features a form to input **URLs** for classification.
- Once the user submits their data, the result (email classification or URL type) is displayed on the same page.

---

## **Example Input/Output**

### **Email Example:**

- **Input**: Upload a **PDF** or **TXT** file with email content.
- **Output**:
  - **Legitimate** (if the email is safe).
  - **Scam/Fake** (if the email is identified as phishing or fraudulent, with a reasoning message).

### **URL Example:**

- **Input**: Enter a URL like `http://example.com`.
- **Output**: The URL is classified as either **Benign**, **Phishing**, **Malware**, or **Defacement**.

---

## **Learnings**

By building this project, students can gain hands-on experience with the following key concepts:

### 1. **Flask Web Development**
   - Learn how to create a web application using **Flask**, including managing routes, handling user inputs, and rendering templates with **Jinja2**.
   - Understand how to integrate **Python** code with **HTML** and serve dynamic content.

### 2. **API Integration with Google Gemini AI**
   - Gain practical experience with integrating third-party **APIs** (like **Gemini AI**) into web applications.
   - Learn how to use generative **AI models** for text and URL classification tasks.
   - Understand the process of interacting with APIs by making requests and handling responses.

### 3. **File Handling and Text Extraction**
   - Learn how to handle **PDF** and **TXT** files in **Python**.
   - Understand how to use libraries like **PyPDF2** to extract text from PDFs.
   - Get experience processing and analyzing text data in real-world applications.

### 4. **Basic Frontend Development**
   - Learn how to build simple **HTML** forms to accept user input.
   - Gain knowledge in using **HTML** and **CSS** to design basic user interfaces for web apps.

### 5. **Security Awareness in Web Applications**
   - Learn about basic **web security** principles by classifying malicious **URLs**.
   - Understand the importance of analyzing content and URLs for **phishing** and **malware** to build more secure applications.

![GitHub Logo](https://github.com/images/logo.png)

