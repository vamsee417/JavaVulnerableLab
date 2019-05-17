pipeline {
    agent any

    stages {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'Maven_home') {
                    sh 'mvn clean compile'
                }
            }
        }

     

        stage ('Package Stage') {
            steps {
                withMaven(maven : 'Maven_home') {
                    sh 'mvn package'
                }
            }
        }
		
		stage('Report Gathering') {
        publishHTML(allowMissing:true, alwaysLinkToLastBuild:false, keepAll:true, reportDir:'target/:'dependency-check-report.html', reportName:'Dcheck')

    }
    }
}
