node("master") 
{ 
  stage ("git-clone") 
    { checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'rajiv-github', url: 'https://github.com/verma-raj/AshokITProject.git']]]) } 
     
   stage("Maven Build") 
   { echo "inside Jenkins"
      sh 'mvn -v || true'
   docker.image('maven:3.8.6').inside{ 
                    sh 'pwd'
                  echo "Inside Maven container "
                    sh 'mvn -v'
		sh 'mvn clean verify'
                    
                }}
   stage("WAR File Ready") 
   { 
	echo " Our WAR file is ready to deploy "
    
   
   }
}
