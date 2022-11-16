properties([parameters([choice(choices: ['master\nfeature1\nfeature2'], name: 'Branches')])])

node("master") 
{ 
  stage ("git-clone") 
    echo " Pulling changes from branch $(params.branch)
    git url: "https://github.com/verma-raj/AshokITProject.git", branch: "$(params.branch)"
     
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
