
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
        
       sleep('sleep') {
            steps {
               "wait_ten_seconds": {
              "Type": "Wait",
              "Seconds": 10,
              "Next": "NextState"
        }
            }
        }
            
        stage('Deploy') {
            steps {
                sh './jenkins/scripts/deliver.sh'
                input message: 'Lanjutkan ke tahap Deploy? (Klik "Abort" untuk mengakhiri)'
                sh './jenkins/scripts/kill.sh'
            }
        }
    }
}
