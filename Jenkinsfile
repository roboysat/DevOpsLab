pipeline {
    agent any
    triggers {
        pollSCM('H/5 * * * *')
        cron('H 0 * * *')
    }
    stages {
        stage('Compile') {
            steps {
                sh 'javac -d bin src/App.java'
                sh 'javac -d bin -cp bin test/AppTest.java'
            }
        }
        stage('Run') {
            steps {
                sh 'java -cp bin App'
                sh 'java -cp bin AppTest'
            }
        }
    }
}
