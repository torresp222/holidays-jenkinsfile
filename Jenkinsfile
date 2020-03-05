#!groovy?
node {
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
