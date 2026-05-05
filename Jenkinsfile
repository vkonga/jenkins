pipeline {
    agent {
        label 'agent-1'
    }

    environment {
        project = 'electronics'
    }

    options {
        timeout(time: 10, unit: 'MINUTES')
        // DisableConcurrentbuild used for build only one build at a time then move next build, it will not run two builds at a time
        disableConcurrentBuilds()
    }   

    // Build
    stages {
        stage('Build') {
            steps {
                script {
                    sh """

                        echo "Hello building"
                        
                        env
                        """
                }
                
            }
        }
        stage('Test') {
            steps {
                script {
                    echo 'Testing...'
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    echo 'Deploying...'
                }
            }
        }
    }

    post {
        always {
            echo 'I will always say hello again!'
            deleteDir() 
        }
        success {
            echo 'Hello success'
        }
        failure {
            echo 'Hello failure'
        }
    }

}