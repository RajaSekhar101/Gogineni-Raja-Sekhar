pipeline {
    agent any

    stages {
        stage('checkout') {
            steps {
               git 'https://github.com/RajaSekhar101/Gogineni-Raja-Sekhar.git'
            }
        }
        stage('build'){
            steps{
                bat 'mvn package'
                
                
            }
        }
            stage('deploy'){
             steps{
                deploy adapters: [tomcat8(credentialsId: '3bc90d6d-675e-4cee-bee5-8f42b51efc13', path: '', url: 'http://localhost:9090')], contextPath: 'servlet-jsp-maven', onFailure: false, war: '**/*.war'
             }
            }
        
        
        }
    }
