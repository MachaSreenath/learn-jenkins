pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
    environment { 
        GREETING = 'Hello Jenkins'
    }
    options {
        timeout(time: 1, unit: 'HOURS')
        disableConcurrentBuilds()
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who are you?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'enter about you')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick what you want')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter password')
    }
    // build
    stages {
        stage('Build') {
            steps {
                echo 'building'
            }
        }
        stage('Test') {
            steps {
                echo 'testing'
            }
        }
        stage('Deploy') {
            steps {
                sh """
                    echo  "shell script likho"
                    echo "$GREETING"
                    #sleep 10
                """
            }
        }
        stage('check params'){
            steps{
                sh """
                    echo "Hello ${params.PERSON}"

                    echo "Biography: ${params.BIOGRAPHY}"

                    echo "Toggle: ${params.TOGGLE}"

                    echo "Choice: ${params.CHOICE}"

                    echo "Password: ${params.PASSWORD}"
                """
            }
        }
    }
    // post build
    post { 
        always { 
            echo 'pipeline fails r success i will execute'
        }
        failure { 
            echo 'pipeline failed'
        }
        success{
            echo 'pipeline success'
        }
    }
}