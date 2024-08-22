pipeline{
    agent any
    tools{
        maven 'Maven'
    }
    stages{
        stage("test"){
            steps{
                // mvn test
                sh '''
                    ls
                    pwd
                    mvn test -X
                '''
            }
        }
        stage("build"){
            steps{
                // mvn package
                sh 'mvn package'
            }
        }
        stage("deploy on test"){
            steps{
                // deploy on container -> plugin
                deploy adapters: [tomcat9(credentialsId: 'tomcat10details', path: '', url: 'http://3.110.41.21:8080/')], contextPath: '/app', war: '**/*.war'
            }
        }
        stage("deploy on prod"){
            steps{
                // deploy on container -> plugin
                deploy adapters: [tomcat9(credentialsId: 'tomcat10details', path: '', url: 'http://13.201.229.18:8080/')], contextPath: '/app', war: '**/*.war'
            }
        }
    }
    post{
        always{
            echo "========always========"
        }
        success{
            echo "========pipeline executed successfully ========"
        }
        failure{
            echo "========pipeline execution failed========"
        }
    }
}
