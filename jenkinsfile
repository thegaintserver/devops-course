pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                echo 'Hello World'
                echo "hi anent"
                sh 'ls -larth /'
            }
        }
        stage('test') {
            steps {
                echo 'Hello World'
                echo "hi anent"
            }
        }
        stage('deploy') {
            steps {
                echo 'Hello World'
                echo "hi anent"
                sh '''
                ls -larth ./
                ls /var/jenkins | wc -l
                '''
            }
        }
    }
    post {
        always {
            echo "Hi after post the build"
        }
        success {
            mail to: "sainigourav48@gmail.com",
            subject: "jenkins job failure",
            body: "jenkins got a job failed for this ${env.BUILD_URL}"
        }
    }
}
