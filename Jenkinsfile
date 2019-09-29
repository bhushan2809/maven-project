pipeline {
  agent any
	
stages	
  {  
	  stage "scm checkout" {
        git 'https://github.com/bhushan2809/maven-project.git'
  }
}	
{
	
	
stage "code test" {
	
	
	steps {
        withMaven(maven: 'Local Maven')
	{
       sh 'mvn test'
       }
   }
 }
}
}
