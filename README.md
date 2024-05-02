# End-to-End Continuous Integration and Continuous Deployment based on GitOps

This repository contains the source code for the End-to-End Continuous Integration and Continuous Deployment based on GitOps project.

## Architecture Overview

We are going to build a CI/CD pipeline that will be triggered by a push to the main branch of the repository. The pipeline will build the application, run the tests, and deploy the application to a Kubernetes cluster. The pipeline will be implemented using GitHub Actions and ArgoCD.

**The architecture of the project is explained below:**

First, we have a GitHub repository that contains the source code of the application. The repository is connected to GitHub Actions, which will be used to build and deploy the application. The GitHub Actions workflow will be triggered by a push to the main branch of the repository. The workflow will build the application, run the tests, and Push the Docker image to Docker Hub. And then It will **Update the Image tag in the Manifest Repository**. The Manifest Repository is a separate GitHub repository that contains the Kubernetes manifests for the application. And our Argo CD will be watching this repository for changes. **Once the image tag is updated in the Manifest Repository, Argo CD will automatically deploy the new version of the application to the Kubernetes cluster**.

## Architecture Diagram

![Architecture Diagram]()

## Prerequisites

- A GitHub account
- A Docker Hub account
- A Kubernetes cluster
- Argo CD installed on the Kubernetes cluster

## Usage

1. Fork this repository and Manifest Repository to your GitHub account.
2. Add the following secrets to your GitHub repository:
   - `DOCKER_USERNAME`: Your Docker Hub username
   - `DOCKER_PASSWORD`: Your Docker Hub password
   - `CI_TOKEN`: A personal access token with the `repo` scope to access the Manifest Repository
3. Update your Argo CD application to watch the Manifest Repository.
4. Push a change to the main branch of the repository to trigger the CI/CD pipeline.

You can Check out my [Medium Article]() for detailed instructions on how to set up the CI/CD pipeline and deploy the application to a Kubernetes cluster based on GitOps.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! If you have any suggestions or run into any issues, feel free to open an issue or create a pull request.

## Author

- [Mathesh M](https://www.linkedin.com/in/mathesh-me/) on LinkedIn.
- You Can also check out my [Medium](https://medium.com/@mathesh-me) for articles on DevOps Tools and Technologies.️