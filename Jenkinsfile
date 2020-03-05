#!groovy?
parallel("stream 1": {    
    node('node1') {
        ws("${env.JOB_NAME}-stream1") {
        stage('Checkout') { // for display purposes
            // Get some code from a GitHub repository
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
           }
         }
        },
            "stream 2": {
                node('node2') {
                    ws("${env.JOB_NAME}-stream2") {
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
