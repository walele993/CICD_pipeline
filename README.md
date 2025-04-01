# CI/CD Pipeline for Node.js Docker Application

**CI/CD Pipeline** is a GitHub Actions workflow designed to automate continuous integration and deployment, ensuring that code changes are automatically tested and deployed. This pipeline streamlines the development process, improves code quality, and accelerates delivery for your Node.js Docker applications.

---

## 🚀 Introduction

This project demonstrates the use of a **CI/CD pipeline** for a **Node.js application** containerized using Docker. It leverages **GitHub Actions** for automated testing, building, and deployment, as well as **GitHub Container Registry** for image storage and distribution.

### Key Features:
- 🚀 **Express.js Web Server**: A simple web server built with **Express.js**.
- 🐳 **Docker Containerization**: Application is containerized for consistent development and deployment.
- 🔄 **Automated CI/CD Pipeline**: Uses GitHub Actions for continuous integration and deployment.
- 📦 **Docker Image Build & Push**: Automatically builds Docker images and pushes them to **GitHub Container Registry** (GHCR).
- ✅ **Automated Test Execution**: Ensures that all tests run before deployment.

---

## 🛠️ Prerequisites

Before starting, ensure you have the following installed:

- **Node.js 14+**
- **Docker 20.10+**
- **GitHub account**
- **Git**

---

## 🧑‍💻 Getting Started

1. **Clone the repository:**
   ```bash
   git clone https://github.com/<your-username>/<repo-name>.git
   cd <repo-name>
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Start the development server:**
   ```bash
   npm start
   ```
   The server will be running on `http://localhost:3000`.

4. **Run tests** (ensure test configurations are set up):
   ```bash
   npm test
   ```

---

## 🐳 Docker Usage

### Build the Docker Image
```bash
docker build -t node-app .
```

### Run the Docker Container
```bash
docker run -p 3000:3000 node-app
```
The application will be accessible at `http://localhost:3000`.

---

## 🔄 CI/CD Pipeline

The automated pipeline triggers when:
- A **push** is made to the `main` branch.
- A **pull request** is created targeting the `main` branch.

### **Workflow Stages:**
1. **Code Checkout**: Pulls the latest changes from the repository.
2. **Node.js Environment Setup**: Installs necessary Node.js versions.
3. **Dependency Installation**: Installs required dependencies from `package.json`.
4. **Test Execution**: Runs automated tests to ensure code quality.
5. **Docker Image Build**: Builds the Docker image of the Node.js application.
6. **GitHub Container Registry (GHCR) Login**: Logs in to GHCR for image storage.
7. **Image Push**: Pushes the Docker image to GHCR for distribution.

---

## 📦 Using Docker Image from GHCR

1. **Login to GHCR:**
   ```bash
   docker login ghcr.io -u <your-username> -p $GITHUB_TOKEN
   ```

2. **Pull the Docker Image:**
   ```bash
   docker pull ghcr.io/<your-username>/node-app:latest
   ```

3. **Run the Docker Container:**
   ```bash
   docker run -p 3000:3000 ghcr.io/<your-username>/node-app:latest
   ```
   Your application will now be available at `http://localhost:3000`.

---

## ⚙️ Configuration

- **Application Port**: Default port is `3000`, configurable in `app.js`.
- **Docker Image Tag**: Change the image tag in the workflow file if needed.
- **Package Visibility**: Configure visibility settings in your GitHub repository (Settings → Packages → node-app).

---

## 🛠️ Troubleshooting

- **Docker Build Errors**: Ensure that required files such as `package.json` and `app.js` are present in the directory.
- **GHCR Authentication Issues**: Make sure the GitHub token has the necessary permissions to push images.
- **Port Conflicts**: Modify the `EXPOSE` port in `Dockerfile` or change the port mapping in `docker run`.
- **Test Failures**: Ensure tests are correctly configured before pushing any changes.

---

## 🤝 Contributing

We welcome contributions to improve this project. Here's how you can help:

- Add more testing frameworks.
- Enhance the pipeline with additional code quality checks.
- Improve deployment strategies for various environments.
- Optimize performance or functionality.

---

## 🏅 Credits

Project created by **Gabriele Meucci** – Focused on automating workflows to improve development efficiency and code quality.

**Happy Coding! 💻**  
*Automate your workflow, accelerate your delivery.*
