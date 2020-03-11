
pipeline 
{
    agent any
    stages 
    {
        stage('build') 
        {
            steps 
            {
                sh 'mvn clean' 
        	}
        }
         stage('test') 
        {
            steps 
            {
                sh 'mvn test' 
        	}
        }
        stage('package') 
        {
            steps 
            {
                sh 'mvn package' 
            }
        }
     	
     	stage('deploy')
     	{
		        when
		        {
		        	expression{(env.BRANCH_NAME == 'master')}
		        }
			        stage('deploy')
			         {
			            steps 
			            {
			                sh 'mvn deploy' 
			            }
			         }
		}
       
 	}
}



