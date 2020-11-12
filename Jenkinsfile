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
                dir('worker'){
                bat 'mvn clean test'
                }

            }
                
        }

        stage('Package'){
            steps{
                when{
                    branch 'master'
                    changeset "**/worker/**"
                }
                echo 'generando binario worker app ...'
                dir('worker'){
                bat 'mvn package -DskipTest'
                archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true

                }
            }
                
        }

    }

       post{

        always{
            echo 'Build para worker app terminado ...'
        }
    }

}