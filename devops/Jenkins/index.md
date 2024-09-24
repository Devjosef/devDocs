# Jenkins

## Introduction
Jenkins is an open-source automation server that helps automate the parts of software development related to building, testing, and deploying, facilitating continuous integration and continuous delivery.

## Basic Syntax
```groovy
// Example of a basic Jenkins pipeline script
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                // Add build steps here
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                // Add test steps here
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                // Add deploy steps here
            }
        }
    }
}
```

## Common Use Cases
- Continuous integration
- Continuous delivery
- Automated testing
- Deployment automation

## Advanced Features
- **Pipeline as Code**: Define your build, test, and deploy pipeline in a Jenkinsfile.
- **Plugins**: Extend Jenkins functionality with a wide range of plugins.
- **Distributed Builds**: Run builds across multiple machines.
- **Declarative and Scripted Pipelines**: Use either declarative or scripted syntax for defining pipelines.

## Code Snippets
### Declarative Pipeline
```groovy
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }
}
```

### Scripted Pipeline
```groovy
node {
    stage('Build') {
        echo 'Building...'
    }
    stage('Test') {
        echo 'Testing...'
    }
    stage('Deploy') {
        echo 'Deploying...'
    }
}
```

### Using Environment Variables
```groovy
pipeline {
    agent any
    environment {
        MY_VAR = 'Hello, World!'
    }
    stages {
        stage('Print Env Var') {
            steps {
                echo "Environment variable: ${env.MY_VAR}"
            }
        }
    }
}
```

### Using Credentials
```groovy
pipeline {
    agent any
    stages {
        stage('Use Credentials') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'my-credentials-id', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
                    echo "Username: ${env.USERNAME}"
                    echo "Password: ${env.PASSWORD}"
                }
            }
        }
    }
}
```

## Tips & Best Practices
- **Use Pipelines**: Define your build, test, and deploy processes in a Jenkinsfile.
- **Modular Pipelines**: Break down complex pipelines into smaller, reusable steps.
- **Use Plugins**: Leverage Jenkins plugins to extend functionality.
- **Security**: Secure your Jenkins instance and use credentials securely.
- **Monitoring**: Monitor your Jenkins instance and pipelines for performance and reliability.

## External Resources
- [Jenkins Official Documentation](https://www.jenkins.io/doc/)
- [Jenkins Pipeline Syntax](https://www.jenkins.io/doc/book/pipeline/syntax/)
- [Jenkins Plugins](https://plugins.jenkins.io/)
- [Jenkins Best Practices](https://www.jenkins.io/doc/book/pipeline/pipeline-best-practices/)
