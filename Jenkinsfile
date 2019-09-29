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
  sshagent (['172.31.41.253']) {
    sh 'scp -o StrictHostKeyChecking=no */target/*.war ec2-user@172.31.41.253:/var/lib/tomcat/webapps'
  }
}
}

}
}
