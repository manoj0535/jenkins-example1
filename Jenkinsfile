pipeline {
    agent any

    stages {
        stage ('Compile Stage') {
            steps {
                withMaven(maven : 'maven3.8') {
                    sh 'mvn clean install'
                }
            }
        }
        stage ('build code') {
            steps {
                sshagent(['jenkins-ec2-privatekey']) {
                sh "scp -o StrictHostKeyChecking=no -i */target/*.jar ubuntu@ec2-3-215-132-134.compute-1.amazonaws.com:/home/ubuntu"
            }
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
//     }
// }