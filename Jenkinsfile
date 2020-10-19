pipeline{
agent{
    label 'linux'
}
tools{
    maven 'maven 3.6.3'
}

stages{
    stage('checkout'){
        steps{
            git "https://github.com/bharat13soni/SimpleMavenProject.git"
        }

    }
    stage('build'){
		steps{
    		sh 'mvn clean compile'
		}
    }
    stage('Test'){
        steps{
            sh 'mvn test'
            junit '**/target/surefire-reports/TEST-*.xml'
        }
    }
    stage('Package'){
        steps{
            sh 'mvn package'
        }
    }

	}
}