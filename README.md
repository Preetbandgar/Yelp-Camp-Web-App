
# 🚀 Yelp Camp Web Application

## 📝 Project Overview

Welcome to **Yelp Camp**, a web app where users can add, view, and rate campgrounds based on their location. This project is inspired by Colt Steele’s Web Developer Bootcamp but includes some tweaks and fixes to make it even better. It’s built with modern tools like Node.js, Express, and MongoDB, and it uses an automated Jenkins pipeline to handle testing and deployment. 

> Note: All project files, including the pipeline and setup details, are in the GitHub repository.

---

## 🏗️ Project Architecture

Yelp Camp is designed as a client-server app:

- **Frontend**: Uses Bootstrap for a clean, mobile-friendly interface.
- **Backend**: Runs on Node.js and Express to manage API requests.
- **Database**: Stores data in MongoDB Atlas, a cloud-based NoSQL database.
- **Authentication**: Secures user logins with Passport.js.
- **Images**: Handles campground photos with Cloudinary.
- **Maps**: Shows campground locations with Mapbox.  
- The app is packaged in a Docker container for easy deployment.

---

## 🛠️ Tech Stack

| Category           | Tools & Technologies                             |
|--------------------|--------------------------------------------------|
| Backend            | Node.js, Express                                 |
| Frontend           | Bootstrap, HTML, CSS, JavaScript                 |
| Database           | MongoDB Atlas                                    |
| Authentication     | Passport.js (Local Strategy)                     |
| Image Storage      | Cloudinary                                       |
| Mapping            | Mapbox                                           |
| Containers         | Docker                                           |
| CI/CD              | Jenkins                                          |
| Artifact Registry  | DockerHub                                        |
| Security Scanning  | Trivy                                            |
| Code Quality       | SonarQube                                        |

---

## ✨ Key Features

- **Campground Management**: Add, view, edit, and delete campgrounds.
- **Reviews & Ratings**: Let users rate and review campgrounds.
- **Interactive Maps**: Show campground locations with Mapbox.
- **Secure Logins**: Protect user accounts with Passport.js.
- **Image Uploads**: Store photos in Cloudinary.
- **Automated Pipeline**: Use Jenkins to test and deploy the app.
- **Code Checks**: Ensure quality with SonarQube and security with Trivy.

---

## 🔄 CI/CD Pipeline

The Jenkins pipeline automates the development process. Here’s how it works:

| Stage                | Description                                           |
|----------------------|-------------------------------------------------------|
| Git Checkout         | Grabs the latest code from GitHub’s main branch.     |
| Install Dependencies | Installs Node.js packages with `npm install`.        |
| Unit Tests           | Runs tests using `npm test`.                          |
| Trivy FS Scan        | Checks the filesystem for security issues.           |
| SonarQube Analysis   | Analyzes code quality for the Campground project.     |
| Docker Build & Tag   | Builds a Docker image and tags it (`Preeet/camp:latest`). |
| Trivy Image Scan     | Scans the Docker image for vulnerabilities.          |
| Docker Push          | Uploads the image to DockerHub.                      |
| Deploy to Dev        | Runs the app on port 3000 in a dev environment.      |

### Pipeline Details

- **Tools**: Node.js 21, SonarQube Scanner  
- **Credentials**: Git (`git-cred`) and DockerHub (`Dockerhub-cred`)  
- **Output**: Deploys the app locally for development

---

## 🔧 Infrastructure Setup

The app runs in a development environment with:

- **DockerHub**: Stores the image (`Preeet/camp:latest`)
- **Jenkins**: Manages the pipeline
- **SonarQube & Trivy**: Check code quality and security
- **MongoDB Atlas**: Handles data storage
- **Cloudinary & Mapbox**: Manage images and maps

---

## 💡 Getting Started

### Prerequisites

- Node.js 21 (for the backend)
- Docker (for containers)
- Jenkins (with Git, Docker, and SonarQube plugins)
- SonarQube (for code analysis)
- Trivy (for security scans)
- Accounts for MongoDB Atlas, Cloudinary, Mapbox, and DockerHub

### Setup Steps

1. **Clone the Repository**:

```bash
git clone https://github.com/jaiswaladi246/3-Tier-Full-Stack.git  
```

2. **Set Up Environment Variables**:

Create a `.env` file in the project root:

```env
CLOUDINARY_CLOUD_NAME=${CLOUDINARY_CLOUD_NAME}  
CLOUDINARY_KEY=${CLOUDINARY_KEY}  
CLOUDINARY_SECRET=${CLOUDINARY_SECRET}  
MAPBOX_TOKEN=${MAPBOX_TOKEN}  
DB_URL=${DB_URL}  
SECRET=${APP_SECRET}
```

> Make sure to define these environment variables securely in your system or CI/CD secret manager.

3. **Configure Jenkins**:

- Install plugins for Git, Docker, and SonarQube
- Add credentials for Git (`git-cred`) and DockerHub (`Dockerhub-cred`)

4. **Set Up SonarQube**:

- Start a SonarQube server and ensure the scanner is ready

5. **Run the Pipeline**:

- Create a Jenkins job with the provided `Jenkinsfile` and run it

6. **Test Locally**:

```bash
docker compose up
```

Visit `http://localhost:3000` in your browser.

---

## 🌟 Project Highlights

- **Fun & Functional**: A campground app with maps and reviews
- **Fully Automated**: Jenkins makes updates a breeze
- **Secure & Clean**: Trivy and SonarQube keep the code solid
- **Cloud-Powered**: Uses MongoDB Atlas, Cloudinary, and Mapbox

---

## 🙏 Acknowledgements

This project was inspired by DevOps Shack and Colt Steele’s Web Developer Bootcamp. Big thanks to the open-source community for tools like Jenkins, Docker, SonarQube, Trivy, MongoDB Atlas, Cloudinary, and Mapbox.

---

## 📬 Contact

Got questions? Check out the repo: `3-Tier-Full-Stack`  
📧 Email: **bandgar.pritam8@gmail.com**
