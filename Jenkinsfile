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

        stage("Codecoverage") {
            steps {
                sh "/bin/sh gradlew test jacocoTestReport"
                publishHTML (target: [
                    reportDir: 'build/reports/jacoco/test/html',
                    reportFiles: 'index.html',
                    reportName: "JaCoCo Report"
                ])
                sh "/bin/sh gradlew test jacocoTestCoverageVerification"
            }
        }
    }
}