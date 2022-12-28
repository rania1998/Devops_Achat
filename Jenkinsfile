pipeline {
    agent any   
 
    stages {
        stage("git pull"){
            steps{
   
                git branch: 'master',
                url: 'https://github.com/rania1998/Devops_Achat.git'
                    
                }
                
            }
       // stage("MVN CLEAN"){
         //  steps{
              
            //   sh 'mvn clean package'
                             
            //   }
                
          //  }
  
       // stage("build"){
          //  steps{
              
              //  sh 'mvn install package'
                             
              //  }
                
         //   }
	    
	      stage('Testing MVN') {
            steps {
                sh """mvn -version"""
            }
        }
       
          stage('MVN CLEAN ') {
            steps {
                echo 'Hello World'
            }
        }
       
          stage('MVN COMPILE ') {
            steps {
                sh 'mvn compile'
            }
        }
	    
        stage("UNIT TEST") {
            steps {
                echo "TESTING project"
                sh 'mvn test -Dmaven.test.failure.ignore=true '
            }
        }
    
       // stage("SonarQube analysis"){
         //   steps{
          //  withSonarQubeEnv('sonarqube-8.9.7') {  
            //    sh 'mvn sonar:sonar'
             //  }
          //   }
            //}
	    stage('MVN SONAR ') {
            steps {
                sh 'mvn sonar:sonar -Dsonar.login=admin -Dsonar.password=sonar'
            }
        }
	    
                
           
        stage('nexus deploy') {
            steps{
               sh 'mvn deploy -DskipTests'
           
         }

      }
        
	
       
    }
	
} 
