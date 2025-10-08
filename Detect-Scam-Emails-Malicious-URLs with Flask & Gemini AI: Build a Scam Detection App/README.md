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
