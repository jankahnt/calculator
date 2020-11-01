pipeline {
    agent any
    stages {
        stage("Compile") {
            steps {
                sh "/bin/sh gradlew compileJava"
            }
        }
        stage("Unit test") {

            steps {
                sh "/bin/sh gradlew test"
            }
        }
    }
}