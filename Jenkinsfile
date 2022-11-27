properties([parameters([gitParameter(branch: '', branchFilter: '.*', defaultValue: '*/dev1', description: 'Select branch from Git', name: 'branch', quickFilterEnabled: false, selectedValue: 'NONE', sortMode: 'NONE', tagFilter: '*', type: 'GitParameterDefinition')])])
script {
          if (env.branch == 'origin/feature1') {
              echo 'I only execute on the feature1 branch'
	      node("small")
		  { stage ("git-clone")
		   	echo " Launching small Instance and cloning GIT "
		   	checkout([$class: 'GitSCM', branches: [[name: '*/$branch']], extensions: [], userRemoteConfigs: [[credentialsId: 'rajiv-github', url: 'https://github.com/verma-raj/AshokITProject.git']]])
		     
		  }
		     stage ("Compiling the code"){ 
    				echo "**** Compiling the code*****"
    				sh 'mvn -v'
    				sh 'mvn clean compile'
		     }
	      
          } else {
                        echo 'I execute elsewhere'
	  }
}
// node{
		
// 	stage ("Test Param")
// 	echo " Pulling changes from branch ${params.branch}"
	
// }
