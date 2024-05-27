pipeline {
    agent any
    environment {
        env = 'deploying_to_prod'
    }
    stages {
        stage('Test stage') {
            steps {
                echo "hi everyone"
                echo "printing ${env}"
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
