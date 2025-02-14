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
    }
}

