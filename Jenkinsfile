pipeline {
    agent any
    stages {
        stage('build-fm1') {
            steps {
            sh 'javac -d . src/*.java'
            sh 'echo Main-Class: Rectangulator > MANIFEST.MF'
            sh 'jar -cvmf MANIFEST.MF rectangle.jar *.class'
            }
        }
        stage('run-fm1') {
            steps {
            sh 'java -jar rectangle.jar 7 9'
            }
        }
    }
    post {
        success {
            archiveArtifacts artifacts: 'rectangle.jar', fingerprint:
            true
        }
    }
}