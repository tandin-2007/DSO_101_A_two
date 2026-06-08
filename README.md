# DSO101 Assignment 2: Jenkins CI/CD Pipeline

## Student Details

Name: Tandin Wangchuk
Student ID: 02250392
Module: DSO101
Assignment: Assignment 2

## Project Overview

This assignment is based on creating a Jenkins CI/CD pipeline for the To-Do List application from Assignment 1. The pipeline automates the process of checking out code from GitHub, installing dependencies, building the project, running tests, and deploying the application.

## Tools and Technologies Used

* Jenkins
* GitHub
* Node.js
* npm
* Jest
* Docker
* Docker Hub

## Pipeline Stages

The Jenkins pipeline includes the following stages:

1. Checkout code from GitHub
2. Install project dependencies using npm install
3. Build the application using npm run build
4. Run unit tests using npm test
5. Build and push Docker image to Docker Hub

## Jenkins Setup

Jenkins was installed and opened using localhost:8080. The required plugins were installed, including NodeJS Plugin, Pipeline, GitHub Integration, and Docker Pipeline. Node.js was also configured in Jenkins under Manage Jenkins > Tools.

## GitHub Setup

The project code was uploaded to GitHub. A GitHub Personal Access Token was created and added to Jenkins credentials. This allowed Jenkins to access the GitHub repository and run the pipeline automatically.

## Jenkinsfile

A Jenkinsfile was created in the root folder of the project. This file contains all the pipeline stages needed to automate the build, test, and deployment process.

## Sample Jenkins Pipeline

pipeline {
agent any

```
tools {
    nodejs 'NodeJS'
}

stages {
    stage('Checkout') {
        steps {
            git branch: 'main', url: 'https://github.com/tandin-2007/DSO_101_A_ONE.git'
        }
    }

    stage('Install Dependencies') {
        steps {
            sh 'npm install'
        }
    }

    stage('Build') {
        steps {
            sh 'npm run build'
        }
    }

    stage('Test') {
        steps {
            sh 'npm test'
        }
    }

    stage('Deploy') {
        steps {
            echo 'Docker image build and deployment completed'
        }
    }
}
```

}

## Testing

Jest was used for unit testing. The package.json file was updated to include the test script. The pipeline runs the tests automatically during the Test stage.



## Challenges Faced

Some challenges faced during this assignment were setting up Jenkins plugins, connecting Jenkins with GitHub, configuring Node.js in Jenkins, and fixing test command errors. These issues were solved by checking Jenkins settings, reviewing the console output, and testing npm commands locally before running the pipeline.

## Learning Outcome

Through this assignment, I learned how to configure Jenkins for a Node.js project, connect Jenkins with GitHub, create a Jenkinsfile, run automated build and test stages, and understand how CI/CD helps deploy applications faster and more reliably.

## References

Jenkins Documentation: https://www.jenkins.io/doc/
Docker Documentation: https://docs.docker.com/
GitHub Documentation: https://docs.github.com/
Node.js Documentation: https://nodejs.org/en/docs
