pipeline {
    agent any
    tools{
        jdk "jdk8"
        maven "maven3"
    }
    stages {
        stage ("Build") {
            steps {
                echo "This is Build Stage"
                sh label: '', script: 'mvn clean package checkstyle:checkstyle'
            }
            post {
                success{
                    echo "Archive Artifacts"
                    archive '**/*.war'
                    echo "publish JUnit Report"
                    junit '**/target/surefire-reports/*.xml'
                    echo "publish Checkstyle Anylishish"
                    checkstyle canComputeNew: false, defaultEncoding: '', healthy: '', pattern: '', unHealthy: ''
                }
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
