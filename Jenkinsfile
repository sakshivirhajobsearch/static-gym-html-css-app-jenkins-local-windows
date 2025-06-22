pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                echo 'Checking out the code...'
                git branch: 'main', url: 'https://github.com/sakshivirhajobsearch/static-gym-html-css-app-jenkins-local-windows.git'
            }
        }

        stage('Build') {
            steps {
                echo 'No build needed for static files.'
            }
        }

        stage('Deploy to Local Server') {
            steps {
                echo 'Deploying static files to local web server...'
                bat '''
                mkdir C:\\xampp\\htdocs\\gymapp
                xcopy /E /Y "%WORKSPACE%" "C:\\xampp\\htdocs\\gymapp\\"
                '''
            }
        }
    }

    post {
        success {
            echo 'Deployment complete. Visit: http://localhost/gymapp/Home.html'
        }
    }
}
