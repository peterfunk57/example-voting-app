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
                    sh 'mvn compile'
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

