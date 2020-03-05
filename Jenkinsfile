#!groovy?
parallel("exec 1": {    
    node {
        ws("${env.JOB_NAME}-1") {
        
        stage('Checkout') { // for display purposes     
            // Get some code from a GitHub repository
        environment {
           JENKINS_PATH = sh(script: 'pwd', , returnStdout: true).trim()  
        }
            checkout ([
                $class: 'GitSCM',
                branches: [[name: '*/es6']],
                extensions: [
                    [$class: 'CheckoutOption', timeout: 30] ,
                    [$class: 'CloneOption', timeout: 30] ,
                    [$class: 'PruneStaleBranch'],
                    [$class: 'CleanCheckout']
                ],
                userRemoteConfigs: [
                    [
                        credentialsId: 'GitHub',
                        url: 'https://github.com/torresp222/accenture-app.git'
                    ]
                ]
            ])
            } 
            script{
                sh 'pwd'
                sh "echo ${JENKINS_PATH}"
            }
          }
         }
        },
            "exec 2": {
                node {
                    ws("${env.JOB_NAME}-2") {
                    stage('Checkout') {
                         checkout ([
                            $class: 'GitSCM',
                            branches: [[name: '*/master']],
                            extensions: [
                                [$class: 'CheckoutOption', timeout: 30] ,
                                [$class: 'CloneOption', timeout: 30] ,
                                [$class: 'PruneStaleBranch'],
                                [$class: 'CleanCheckout']
                            ],
                            userRemoteConfigs: [
                                [
                                    credentialsId: 'GitHub',
                                    url: 'https://github.com/torresp222/juego-ahorcado.git'
                                ]
                            ]
                        ])
                        }
                       }
                    }
                }
   )
