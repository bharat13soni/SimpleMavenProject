pipeline{
agent any
tools{
    maven 'maven 3.6.3'
}

stages{
    stage('checkout'){
        steps{
            git url: "https://github.com/bharat13soni/SimpleMavenProject.git", branch: 'main'
        }

    }
    stage('build'){
		steps{
    		bat 'mvn clean compile'
		}
    }
    stage('Test'){
        steps{
            bat 'mvn test'
            junit '**/target/surefire-reports/TEST-*.xml'
        }
    }
    stage('Package'){
        steps{
            bat 'mvn package'
        }
    }

	}
}