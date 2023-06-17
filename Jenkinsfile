lnv@LNV25U:~/Documents/react/a428-cicd-labs$ cat Jenkinsfile 
    pipeline {
        agent {
            docker {
                image 'node:16-buster-slim' 
                args '-p 3000:3000' 
            }
        }
        stages {
            stage('Build') { 
                steps {
                    sh 'npm install' 
                }
            }
        stage('Test') { 
            steps {
                sh './jenkins/scripts/test.sh' 
            }
        }
    }
}
