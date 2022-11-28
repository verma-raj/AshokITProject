properties([parameters([gitParameter(branch: '', branchFilter: '.*', defaultValue: '*/master', description: 'Select branch from Git', name: 'branch', quickFilterEnabled: false, selectedValue: 'NONE', sortMode: 'NONE', tagFilter: '*', type: 'GitParameterDefinition')])])
script {
          
		  node("medium")
		  { 
			  stage ("git-clone") {
		   		echo " Launching small Instance and cloning GIT from $thisbranch  and ${params.branch} "
		   		checkout([$class: 'GitSCM', branches: [[name: params.branch]], extensions: [], userRemoteConfigs: [[credentialsId: 'git-user', url: 'https://github.com/verma-raj/AshokITProject.git']]])
			  }
		 
		     stage ("Compiling the code") { 
    				echo "**** Compiling the code inside feature2 *****"
    				sh 'mvn -v'
    				sh 'mvn clean packahe'
		     }
	      
          	} 
	  }
	
}
