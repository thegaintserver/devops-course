pipeline {
    agent any
    parameters {
        string(name: 'NAME', description: 'enter your name')
        text(name: 'Text', description: 'share details')
        choice(name: 'choice', choices: ['Main', 'feature'], description: 'choose branch')
        booleanParam(name: 'SKIP_TEST', description: 'lets skip the build? Yes or No')
        password(name: 'put_your_password', description: 'enter password')
    }
    stages {
        stage('Test stage') {
            steps {
                echo "hello text : ${params.Text}"
                echo "hello boolean : ${params.SKIP_TEST}"
                echo "hello password : ${params.put_your_password}"
                echo "hello string ${params.NAME}"
                echo "hello choice : ${params.choice}"
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
