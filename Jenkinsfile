pipeline {
    agent any
    stages {
        stage ("Build") {
            steps {
                Echo "This is Build Stage"
            }
        }
        stage ('Deploy-Dev'){
            steps {
                echo "This is Development Deployment Stage"
            }
        }
        stage ('Deploy-Prod') {
            steps {
                echo "This is Production Deployment Stage"
            }
        }
    }
}
