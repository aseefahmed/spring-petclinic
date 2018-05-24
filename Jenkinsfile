pipeline {
	agent {docker 'maven:3.5-alpine'}
	stages {
		stage('checkout'){
			steps{
				git 'https://github.com/aseefahmed/spring-petclinic.git'
			}
		}
		stage('build'){
			steps{
				sh 'mvn clean package'
				junit '**/target/surefire-reports/TEST-*.xml'
			}
		}
	}
}
