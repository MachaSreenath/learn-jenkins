pipeline {
    agent{
        node{
            label 'AGENT-1'
        }
    }
    // build
    stages {
        stage('Build') {
            steps {
                echo 'hello'
                }
    }
    stage('Deploy') {
        steps {
            echo 'world'
            }
   }
   stage('example'){
    steps {
        echo 'exampleworld'
   }
   }
    }
    // post build
post {
    always {
        echo 'i will always say hello again'
    }
    failure {
        echo 'this runs when pipeline is failed, used generally to send some allerts'
    }
    success {
        echo 'executes when pipeline is success'
    }
    }
}

