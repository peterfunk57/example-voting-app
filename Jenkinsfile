pipeline {

    agent any

    tools {
        maven 'Maven 3.6.1' 
    }

    stages{

        stage('build'){
            steps{
                echo 'Compilando worker app ...'
                dir('worker'){
                    mvn compile
                }
                
            }

        }

        stage ('test'){
            steps{
                echo 'Corriendo pruebas unitstias worker app ...'
            }

        }

        stage('package'){
            steps{
                echo 'Empacando worker app ...'
            }

        }
    }
    
    post{

        always{
            echo 'Build para worker app terminado ...'

        }
    }
}

