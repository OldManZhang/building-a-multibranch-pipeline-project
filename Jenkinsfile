pipeline {
    agent {
        docker {
            image 'node:6-alpine'
            args '-p 3000:3000 -p 5000:5000' 
        }
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                echo "build"
            }
        }
        stage('Test') {
            steps {
            	echo "test env CI value : ${CI}"
	    }

        }
        stage('Delivery') {
	    when {
	       branch 'development'
	    }
            steps {
            	echo "Delivery"
	    }

        }
        stage('Deploy') {
            when{
	       branch 'Production'
	    }
	    steps {
            	echo "Deploy"
	    }

        }
    }
}
