pipeline {
    agent any

    stages {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'maven3.8') {
                    sh 'mvn clean install'
                }
            post {
               success {
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts: '**/target/*.jar'
                   }
              } 
            }
        }
        // stage ('delivery') {
        //     step {
        //         sh 'scp -v -o StrictHostKeyChecking=no -i target/*.jar ubuntu@3.215.132.134:/home/ubuntu'
 
        //     }
        // }
        // stage ('Deployment Stage') {
        //     steps {
        //         withMaven(maven : 'maven3.8') {
        //             sh 'mvn deploy'
        //         }
        //     }
        // }
    }
}