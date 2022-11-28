properties([parameters([gitParameter(branch: '', branchFilter: '.*', defaultValue: '*/dev1', description: 'Select branch from Git', name: 'branch', quickFilterEnabled: false, selectedValue: 'NONE', sortMode: 'NONE', tagFilter: '*', type: 'GitParameterDefinition')])])

script {
          if (env.branch == 'origin/feature1') {
              def thisbranch = env.branch
		  echo "I only execute on the $thisbranch branch"
		  echo " This is what i Get - ${params.branch}"
	      node("small")
		  { 
			  stage ("git-clone") {
		   		echo " Launching small Instance and cloning GIT from $thisbranch  and ${params.branch} "
		   		checkout([$class: 'GitSCM', branches: [[name: params.branch]], extensions: [], userRemoteConfigs: [[credentialsId: 'git-user', url: 'https://github.com/verma-raj/AshokITProject.git']]])
			  }
		 
		     stage ("Compiling the code") { 
    				echo "**** Compiling the code*****"
    				sh 'mvn -v'
    				sh 'mvn clean compile'
		     }
	      
          	} 
	  }
	if (env.branch == 'origin/feature2') {
	def thisbranch = env.branch
	echo "I only execute on the $thisbranch branch"
		node("medium")
		{ stage ("git-clone")
	 	echo " Launching small Instance and cloning GIT from $thisbranch "
		}
	}
	else {
                        echo 'I execute elsewhere'
	}
}
		  def thisbranch = env.branch
	      node("small")
		  { stage ("git-clone")
		   	echo " Launching small Instance and cloning GIT from $thisbranch "
		   	checkout([$class: 'GitSCM', branches: [[name: '*/feature1']], extensions: [], userRemoteConfigs: [[credentialsId: 'git-user', url: 'https://github.com/verma-raj/AshokITProject.git']]])
		     
		  }
		     stage ("Compiling the code"){ 
    				echo "**** Compiling the code*****"
    				sh 'mvn -v'
    				sh 'mvn clean compile'
		     }
	      
          } 
	if (env.branch == 'origin/feature2') {
	def thisbranch = env.branch
	echo "I only execute on the $thisbranch branch"
		node("medium")
		{ stage ("git-clone")
	 	echo " Launching small Instance and cloning GIT from $thisbranch "
		}
	}
	else {
                        echo 'I execute elsewhere'
	}
}
