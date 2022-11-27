properties([parameters([gitParameter(branch: '', branchFilter: '.*', defaultValue: '*/dev1', description: 'Select branch from Git', name: 'branch', quickFilterEnabled: false, selectedValue: 'NONE', sortMode: 'NONE', tagFilter: '*', type: 'GitParameterDefinition')])])
script {
          if (${params.branch} == 'origin/feature1') {
              echo 'I only execute on the feature1 branch'
          } else {
                        echo 'I execute elsewhere'
	  }
}
// node{
		
// 	stage ("Test Param")
// 	echo " Pulling changes from branch ${params.branch}"
	
// }
