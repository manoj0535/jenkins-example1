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

        // stage ('Deployment Stage') {
        //     steps {
        //         withMaven(maven : 'maven3.8') {
        //             sh 'mvn deploy'
        //         }
        //     }
        // }
    }
}