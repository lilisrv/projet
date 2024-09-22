pipeline {
	agent any
	stages {
	 stage ('Build Angular') {
	      steps {
		 dir('angular') {
			sh 'docker build -t angular-app .'
		}
              }
           }
	   stage ('Build Spring Boot') {
		steps {
		   dir('springboot') {
                        sh 'docker build -t springboot-boot-app.'
				}
			    }
                       }
			stage('Deploy with Docker compose') {
			    steps {
				sh 'docker-compose up -d'
			     }
                         }
                     }
                 }
