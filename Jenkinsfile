pipeline{
    agent any 

    tools{
        maven 'Maven-3.9.16'
    }

    stages{
        stage('Initialize'){
            steps{
                echo 'starting the build process...'
                sh 'mvn --version'
            }

        }

        stage('Compile and Unit test'){
            steps{
                echo 'Compileing the code and running unit test...'
                sh 'mvn clean test'
            }  
            post{
                success{
                    junit '**/target/surefire-repoerts/*.xml'
                }
                failure{
                    echo 'Unit test failed...'
                }
            }        

        }

    }
}