pipeline {
    agent any
	environment {
		DOCKERHUB_CREDENTIALS=credentials('dockerhub')
	}
 stages {
  stage('Docker Build and Tag') {
           steps {
              
                echo 'docker build -t activemq:latest .' 
                echo  'docker tag activemq:latest antonyjebinraj/corbandocker:activemq'
                echo 'docker tag activemq:latest antonyjebinraj/corbandocker:$BUILD_NUMBER'
               
          }
        }
  stage('Login') {

			steps {
				echo 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
			}
		}
	stage('Push') {

			steps {
				echo 'docker push antonyjebinraj/corbandocker:activemq'
			}
		}
    }
}