pipeline{
    agent any
    stages {
        stage(git){
            steps{ 
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
                deploy adapters: [tomcat9(credentialsId: 'lavanya', path: '', url: 'http://13.234.32.138:4444/')], contextPath: 'lavanya', war: '**/*.war'
            }
        }
    }
}
