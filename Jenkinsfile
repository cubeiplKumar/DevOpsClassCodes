
pipeline{
    tools{
        jdk 'myjava'
        maven 'mymaven'
    }
	agent any
      stages{
           stage('Checkout'){
	    
               steps{
		 echo 'cloning..'
                 git 'https://github.com/akshu20791/DevOpsClassCodes.git'
              }
          }
          stage('Compile'){
             
              steps{
                  echo 'compiling..'
                  bat 'mvn compile'
	      }
          }
          stage('CodeReview'){
		  
              steps{
		    
		  echo 'codeReview'
                  bat 'mvn pmd:pmd'
              }
          }
           stage('UnitTest'){
		  
              steps{
	         
                  bat 'mvn test'
              }
               post {
               success {
                   junit 'target/surefire-reports/*.xml'
               }
           }	
          }
          
          stage('Package'){
		  
              steps{
		  
                  bat 'mvn package'
              }
          }
	     
          
      }
}
