pipeline{
	agent any
	tools{
	maven 'Maven'
	}
	stages{
		stage('Checkout'){
			steps{
				git branch:'master',url:'https://github.com/Kavya-nyamagoud/MyMavenApp_test01.git'
			}
		}
		stage('Build'){
			steps{
				sh 'mvn clean package'
			}
		}
		stage('Test'){
			steps{
				sh 'mvn test'
			}
		}
		stage('Run application'){
			steps{
				sh 'java -jar target/MyMavenApp_test01-1.0-SNAPSHOT.jar'
			}
		}
	}
	post{
		success{
			echo 'Build and Deployment succesful'
		}
		failure{
			echo 'Build failed'
		}
	}
}
