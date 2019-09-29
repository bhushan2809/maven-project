pipeline {
  agent any
	
stages	
  {  
	  stage "scm checkout" {
        git 'https://github.com/bhushan2809/maven-project.git'
  }
}	
{
	
	
stage ('code test') {
	
	
	steps {
        withMaven(maven: 'localmaven')
	{
       sh 'mvn test'
       }
   }
 }
}
}
