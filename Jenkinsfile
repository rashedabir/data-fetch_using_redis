pipeline {
    agent { label 'DevOps-Dev' }
    tools { nodejs "NodeJS" } // Replace with your Node.js tool name

    stages {
        stage('SCM Check out') {
            steps {
                echo 'Git clone has done successfully'
            }
        }

        stage('NPM Install and Build') {
            steps {
                sh 'npm ci' // Use 'npm ci' for a more deterministic install, or 'npm install' if needed
                echo 'Successfully Installed NPM dependencies and built the Node.js application.'
            }
        }

        stage('Start Node.js with PM2') {
            steps {
                sh 'pm2 start app.js --name "REDIS_TEST"' // Replace with your Node.js entry point and app name
                echo 'Successfully started the Node.js application with PM2.'
            }
        }

        stage('Run Project') {
            steps {
                echo 'Project Successfully Done.'
            }
        }
    }
}
