pipeline{
    agent any
    tools{
        maven 'Maven'
    }
    stages{
        stage("test"){
            steps{
                // mvn test
                sh 'mvn --version'
                echo "========executing A========"
            }
        }
        stage("build"){
            steps{
                // mvn package
                echo "========executing A========"
            }
        }
        stage("deploy on test"){
            steps{
                // deploy on container -> plugin
                echo "========executing A========"
            }
        }
        stage("deploy on prod"){
            steps{
                // deploy on container -> plugin
                echo "========executing A========"
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
