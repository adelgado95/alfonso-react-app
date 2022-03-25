pipeline {
    agent any
    stages {
        stage("Build") {
            steps {
                sh "sudo npm install"
            }
        }
        stage("Test") {
            steps {
                sh "sudo npm run lint"
		sh "sudo npm run prettier"
		sh "sudo npm run test"
            }
        }
        stage("Deploy") {
            steps {
                sh "sudo rm -rf /var/www/alfonso-react-app"
                sh "sudo cp -r ${WORKSPACE}/build/ /var/www/alfonso-react-app/"
            }
        }
    }
}

