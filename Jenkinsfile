pipeline{
  agent any
  tools {
    maven 'Maven_3.5.4' 
  }
 environment {
    ANYPOINT = credentials('ANYPOINT')
 }
 stages {
 	stage ('Build'){
 		steps {
		
 				bat 'mvn -f pom.xml clean install'
 			
 		}
 	}
 	stage ('Deploy'){
 		steps {
 				bat 'mvn -f pom.xml package deploy  -Dusername=$ANYPOINT_USR -Dpassword=$ANYPOINT_PSW -Denvironment=Sandbox -DmuleDeploy'
 			
 		}
 	}
 }

}
