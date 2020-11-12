pipeline {

    agent any

    tools {
        maven 'Maven 3.6.3' 
    }

    stages{

        stage('build'){
            steps{
                echo 'Compilando worker app ...'
                dir('worker'){
                bat 'mvn compile'
                }
            }
                
        }

        stage('Testing'){
            steps{
                echo 'Testing worker app ...'

                }
                
        }

        stage('Package'){
            steps{
                echo 'generando binario worker app ...'

                }
                
        }

    }

       post{

        always{
            echo 'Build para worker app terminado ...'

        }
    }

}