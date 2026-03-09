pipeline {
    agent any

    stages {
        stage('Fetch') {
            steps {
                echo 'Fetching the file'
                git 'https://github.com/gargi250804-ctrl/devopsprac.git'
            }
        }
        stage('Build') {
            steps {
                echo 'Building in process......'
                bat 'javac Hello.java'
            }
        }
        stage('Publish') {
            steps {
                publishHTML([
                 allowMissing:true,
                 alwaysLinkToLastBuild:false,
                 keepAll:false,
                 reportDir:'.',
                 reportFiles:'Index.html',
                 reportName:'MY HTML PAGE'])
            }
        }
    }
        post{
            success{
                echo 'Pipeline built successfully'
            }
            failure{
                echo 'Pipeline Failed'
            }
        }
}
