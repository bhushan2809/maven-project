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
	stage ('code install') {
		
		steps {
		withMaven(maven: 'localmaven')
			{
				sh 'mvn install'
			}
		}
	}
	stage ('deploy to tomcat') {	   
	   
	   steps {
  sshagent (['18.195.35.105']) {
    sh 'scp -o StrictHostKeyChecking=no */target/*.war ec2-user@18.195.35.105:/var/lib/tomcat/webapps'
  }
}
}

}
}
