pipeline{
	agent any
	tools{
		maven "test-maven"
	}
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
                  sh 'mvn compile'
	      }
          }
          stage('CodeReview'){
		  
              steps{
		    
		  echo 'codeReview'
                  sh 'mvn pmd:pmd'
              }
          }
           stage('UnitTest'){
		  
              steps{
	         
                  sh 'mvn test'
              }
               post {
               success {
                   junit 'target/surefire-reports/*.xml'
               }
           }	
          }
          
          stage('Package'){
		  
              steps{
		  
                  sh 'mvn package'
              }
          }
	     
          
      }
}
