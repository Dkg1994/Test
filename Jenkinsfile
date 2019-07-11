pipeline {
    agent any
    

  environment {
  
    PATH = "C:\Users\devendra.gupta\AppData\Local\Programs\Git\bin;C:\Users\devendra.gupta\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Git;${env.PATH}"
    
  stages {
    stage('Sanity check') {
      steps {
        sh 'script/code_scan.sh'
      }
    }

    stages {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'Maven Machine') {
                    sh 'mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'Maven Machine') {
                    sh 'mvn Test1'
                }
            }
        }


        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'Maven Machine') {
                    sh 'mvn deploy'
                }
            }
        }
    }
}