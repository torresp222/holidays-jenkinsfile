#!groovy?
//parallel("exec 1": {    
node {
        //def pwd = env.WORKSPACE
       // def user = "vagrant"
        //def host = "10.145.5.249"
        //def base_path = "/var/www"
        //ws("${env.JOB_NAME}-1") {
        //def workspace = env.WORKSPACE
           stage('Checkout1') { // for display purposes     
                // Get some code from a GitHub repository
                checkout ([
                    $class: 'GitSCM',
                    branches: [[name: '*/es6']],
                    extensions: [
                        [$class: 'CheckoutOption', timeout: 30] ,
                        [$class: 'RelativeTargetDirectory', relativeTargetDir: 'back'],
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
                //def workspace = env.WORKSPACE
               // echo "First workspace directory is ${pwd}"
                //echo "workspace directory is ${workspace}"
                }
           /* stage('Build'){
                def user = "vagrant"
                def host = "10.145.5.249"
                def base_path = "/var/www"
                sh "ssh $user@$host \"sudo install -d -o $user -g $user -m 775 $base_path/releasesback/${BUILD_ID}/\""
                sh "cd ${workspace} && tar czf ${BUILD_ID}.tar.gz *"
                sh "scp -r ${BUILD_ID}.tar.gz $user@$host:$base_path/releasesback/${BUILD_ID}/"
                sh "ssh $user@$host \"tar -xzvf $base_path/releasesback/${BUILD_ID}/${BUILD_ID}.tar.gz -C $base_path/releasesback/${BUILD_ID}/\""
            }*/
         //}
         /*stage('Borrar checkout'){
            sh "rm -rf /var/lib/jenkins/${env.JOB_NAME}-1"
          }*/
         //}
        //},
          //  "exec 2": {
       // node {
        //def user = "vagrant"
                    //def host = "10.145.5.249"
                    //def base_path = "/var/www"
                    //ws("${env.JOB_NAME}-2") {
        stage('Checkout2') {
            checkout ([
                $class: 'GitSCM',
                branches: [[name: '*/master']],
                    extensions: [
                       [$class: 'CheckoutOption', timeout: 30] ,
                       [$class: 'RelativeTargetDirectory', relativeTargetDir: 'front'],
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
                //    }
              //  }
  // )
