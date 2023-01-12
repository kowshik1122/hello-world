pipeline {
    agent any
    
    environment {
        PATH = "/usr/share/maven/bin:$PATH"
    }

    stages {
        stage('1') {
            steps {
                git 'https://github.com/Raj-358/hello-world.git'
            }
        }
        stage('2') {
            steps {
                sh "mvn clean install"
            }
        }
         stage('4') {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'user_deployer', path: '', url: 'http://20.55.84.35:9090')], contextPath: null, war: '**/*.war'
            }
        }
    }
}
