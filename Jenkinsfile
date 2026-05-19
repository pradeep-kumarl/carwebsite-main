pipeline {
    agent any

    stages {

        stage('Clone from GitHub') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/pradeep-kumarl/carwebsite-main.git'
            }
        }

        stage('Deploy to Apache') {
            steps {
                sh '''
                    sudo cp -r * /var/www/html/
                    sudo systemctl restart httpd
                '''
            }
        }
    }

    post {
        success {
            echo '✅ Car Website Deployed Successfully!'
        }
        failure {
            echo '❌ Deployment Failed!'
        }
    }
}
