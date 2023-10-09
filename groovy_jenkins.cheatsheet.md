Jenkins Groovy DSL (Domain-Specific Language) cheat sheet to help you work with Groovy scripts for Jenkins Pipeline, Job DSL, and other Jenkins automation tasks:

**Groovy Basics:**
- Groovy is a dynamic scripting language for the Java Virtual Machine (JVM) with a syntax similar to Java.
- Groovy scripts in Jenkins are used for defining Pipeline jobs, Job DSL scripts, and various automation tasks.

**Jenkins Pipeline:**
- A Jenkinsfile is a Groovy script used to define and configure Pipeline jobs.
- Common Jenkins Pipeline stages:
  ```groovy
  pipeline {
      agent any
      stages {
          stage('Build') {
              steps {
                  // Build steps here
              }
          }
          stage('Test') {
              steps {
                  // Test steps here
              }
          }
          stage('Deploy') {
              steps {
                  // Deployment steps here
              }
          }
      }
  }
  ```

**Job DSL:**
- Job DSL allows you to define and manage Jenkins jobs programmatically using Groovy scripts.
- Common Job DSL script elements:
  ```groovy
  // Create a new Jenkins job
  job('MyJobName') {
      // Job configuration here
  }

  // Define job parameters
  parameters {
      stringParam('MY_PARAM', 'default_value', 'Description')
  }

  // Add build steps
  steps {
      shell('echo "Build step"')
  }

  // Configure SCM (Source Code Management)
  scm {
      git('https://github.com/repo.git')
  }
  ```

**Variables:**
- Define and use variables in Groovy scripts:
  ```groovy
  def myVariable = 'Hello, Jenkins!'
  echo myVariable
  ```

**Conditional Statements:**
- Use if-else conditions in Groovy:
  ```groovy
  if (condition) {
      // Code block to execute if the condition is true
  } else {
      // Code block to execute if the condition is false
  }
  ```

**Loops:**
- Use loops like for and while in Groovy scripts:
  ```groovy
  for (int i = 0; i < 5; i++) {
      // Loop body
  }

  int counter = 0
  while (counter < 10) {
      // Loop body
      counter++
  }
  ```

**Methods and Functions:**
- Define and use functions/methods in Groovy:
  ```groovy
  def myFunction(param1, param2) {
      // Function body
      return param1 + param2
  }

  def result = myFunction(2, 3)
  echo "Result: ${result}"
  ```

**String Manipulation:**
- Perform string operations in Groovy:
  ```groovy
  def str1 = 'Hello'
  def str2 = 'Jenkins'
  def combined = "${str1}, ${str2}!"
  echo combined
  ```

**Environment Variables:**
- Access environment variables in Jenkins Groovy scripts:
  ```groovy
  def buildNumber = env.BUILD_NUMBER
  def workspace = env.WORKSPACE
  echo "Build Number: ${buildNumber}"
  echo "Workspace: ${workspace}"
  ```

**Console Output:**
- Print messages to the console output:
  ```groovy
  echo 'This is a message'
  ```
