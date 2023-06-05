pipeline {
    agent any
    stages {
        stage (git){
            steps {
                git branch: 'month', url: 'https://github.com/LIKITH-coder/likithrepo.git'
            }
        }
        stage(build){
            steps{
                sh 'mvn clean package'
            }
        }
        stage (deploy){
            steps{
                deploy adapters: [tomcat9(credentialsId: 'maven', path: '', url: 'http://13.126.193.100:4444/')], contextPath: 'month', war: '**/*.war'
            }
        }
    }
}
