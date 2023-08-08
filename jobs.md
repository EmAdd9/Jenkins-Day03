```markdown
# Jenkins Job Tutorial

In this tutorial, we'll guide you through creating three types of Jenkins jobs: Freestyle, Pipeline, and Multibranch. Each job will include stages for Git checkout, Maven compile, Maven package, and deploying to Tomcat. Let's dive in!

## Freestyle Job

1. From the Jenkins dashboard, click on "New Item" to create a new job.
2. Enter a name for the job and select "Freestyle project" as the job type.
3. In the job configuration page, navigate to the "Source Code Management" section and choose your Git repository. Configure the branch or repository URL as needed.
4. In the "Build" section, click on "Add build step" and select "Execute shell" from the dropdown.
5. In the shell script section, enter the following commands:

```bash
#!/bin/bash
# Git checkout
git checkout <branch_name>
# Maven compile
mvn compile
# Maven package
mvn package
# Deploy to Tomcat
# Replace 'webapp.war' with your generated WAR file name and adjust the Tomcat server details
cp target/webapp.war /path/to/tomcat/webapps/
```

6. Click "Save" to save the job configuration.

## Pipeline Job

1. From the Jenkins dashboard, click on "New Item" to create a new job.
2. Enter a name for the job and select "Pipeline" as the job type.
3. In the job configuration page, scroll down to the "Pipeline" section.
4. Choose the "Pipeline script" option and enter the following script:

```groovy
pipeline {
  agent any
  
  tools {
    jdk 'jdk11'
    maven 'maven3'
  }
  
  stages {
    stage('Git Checkout') {
      steps {
        // Git checkout
        git branch: '<branch_name>', url: '<git_repository_url>'
      }
    }
    
    stage('Maven Compile') {
      steps {
        // Maven compile
        sh 'mvn compile'
      }
    }
    
    stage('Maven Package') {
      steps {
        // Maven package
        sh 'mvn package'
      }
    }
    
    stage('Deploy to Tomcat') {
      steps {
        // Deploy to Tomcat
        sh 'cp target/webapp.war /path/to/tomcat/webapps/'
      }
    }
  }
}
```

5. Click "Save" to save the job configuration.

## Multibranch Job

1. From the Jenkins dashboard, click on "New Item" to create a new job.
2. Enter a name for the job and select "Multibranch Pipeline" as the job type.
3. In the job configuration page, go to the "Branch Sources" section.
4. Configure the source for your Git repository (e.g., GitHub, Bitbucket) and provide necessary credentials and repository details.
5. In the "Build Configuration" section, click on "Add build step" and select "Pipeline script" from the dropdown.
6. Enter the same pipeline script mentioned in the Pipeline Job section.
7. Click "Save" to save the job configuration.

That's it! You've successfully created three Jenkins jobs: Freestyle, Pipeline, and Multibranch. Each job contains stages for Git checkout, Maven compile, Maven package, and deploying to Tomcat. You can manually trigger these jobs or set them up to run automatically based on your requirements.

Happy Jenkins automation!
```
