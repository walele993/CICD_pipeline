# CI/CD Pipeline

**CI/CD Pipeline** is a GitHub Actions workflow designed to automate the process of continuous integration and continuous deployment, ensuring that code changes are automatically tested and deployed. This pipeline focuses on streamlining the development process, improving code quality, and accelerating delivery.

# Node.js Docker Application with CI/CD Pipeline

A simple Node.js application containerized with CI/CD pipeline using GitHub Actions and GitHub Container Registry.

## Features

- Basic Express.js web server
- Docker containerization
- Automated CI/CD pipeline
- Automatic Docker image builds pushed to GitHub Container Registry
- Automated test execution

## Prerequisites

- Node.js 14+
- Docker 20.10+
- GitHub account
- Git

## Getting Started

1. Clone the repository:
```
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
```
2. Install dependencies:
```
npm install
```

3. Start the development server:
```
npm start
```

4. Run tests (ensure tests are configured):
```
npm test
```

## Docker Usage

### Build the image
```
docker build -t node-app .
```

### Run the container
```
docker run -p 3000:3000 node-app
```

Application will be available at: http://localhost:3000

## CI/CD Pipeline

The automated pipeline triggers on:
- Push to `main` branch
- Pull request to `main` branch

**Workflow stages:**
1. Code checkout
2. Node.js environment setup
3. Dependency installation
4. Test execution
5. Docker image build
6. GitHub Container Registry (GHCR) login
7. Image push to GHCR

### Using Docker Image from GHCR

1. Login to GHCR:
```
docker login ghcr.io -u <your-username> -p $GITHUB_TOKEN
```

2. Pull the image:
```
docker pull ghcr.io/<your-username>/node-app:latest
```

3. Run the container:
```
docker run -p 3000:3000 ghcr.io/<your-username>/node-app:latest
```

## Configuration

- **Application port**: 3000 (modifiable in `app.js`)
- **Docker image tag**: Edit the workflow file to change naming
- **Package visibility**: Configure in GitHub repository settings (Settings → Packages → node-app)

## Troubleshooting

- **Docker build errors**: Verify required files exist (package.json, app.js)
- **GHCR auth issues**: Ensure GitHub token has correct permissions
- **Port conflicts**: Modify `EXPOSE` port in Dockerfile and `docker run` command
- **Test failures**: Verify test configuration before pushing changes

## Contributing

We welcome contributions in the following areas:
- Additional testing frameworks.
- Enhanced code quality checks.
- Improved deployment strategies.
- Performance optimizations.

## Credits

Created by **Gabriele Meucci** – Focusing on automating development workflows and improving code quality.

**Happy coding! 💻**
*Automate your workflow, accelerate your delivery.*
