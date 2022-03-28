pipeline {
    agent any
     tools {
        nodejs '16.14.0'
    }
    stages {
        stage("Build") {
            steps {
                sh "npm install"
                
            }
        }
        stage("Test") {
            steps {
                sh "npm run lint"
                sh " npm run prettier"
                sh "npm run test"
            }
        }
        stage("Deploy") {
            steps {
                sh " npm run build"
                sh "sudo rm -rf /var/www/alfonso-react-app"
                sh "sudo cp -r ${WORKSPACE}/build/ /var/www/alfonso-react-app/"
            }
        }
    }
}

