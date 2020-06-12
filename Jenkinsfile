pipeline {
    agent any
    stages{
        stage('Build') {
            
            steps {
            bat 'composer install'
            }
        }
    
        stage('Test') {
            steps {
                bat 'php --version'
                bat './vendor/bin/phpunit --testsuite Unit'
            }
        }
    
        stage('Deploy') {
            steps {
                bat 'php artisan migrate'
            }
        }
    
        stage ('Test Feature') {
            steps {
                bat './vendor/bin/phpunit --testsuite Feature'
            }
        }
    }
}