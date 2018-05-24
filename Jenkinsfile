pipeline {
	agent {docker 'maven:3.5-alpine'}
	stages {
		stage('checkout'){
			steps{
				git 'https://github.com/aseefahmed/spring-petclinic.git'
			}
		}
		stage('Duild'){
			steps{
				sh 'mvn clean package'
				junit '**/target/surefire-reports/TEST-*.xml'
                                archiveArtifacts artifacts: 'target/*.war', fingerprint: true
			}
		}
                stage('Deploy'){
                        input 'Do you want to proceed for deployment?'
                }
	}
}
