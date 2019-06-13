pipeline {
    agent any
    
    stages {
        stage('Preparations') {
            steps{
                echo 'Preparing...'
		sh './gradlew clean test jar'
            }
        }
	stage('Build'){
	    steps{
		echo 'Building...'
                sh './gradlew clean test jar'	    
	    }
        }
        stage('Result'){
	    steps{
	        echo 'Results...'
		junit '**/build/test-results/test/TEST-*.xml'
	        archive 'build/libs'        
	    }
        }
    }
}
