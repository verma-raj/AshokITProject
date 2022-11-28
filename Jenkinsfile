pipeline {
    agent any
    parameters {
        properties([parameters([gitParameter(branch: '', branchFilter: '.*', defaultValue: '*/dev1', description: 'Select branch from Git', name: 'branch', quickFilterEnabled: false, selectedValue: 'NONE', sortMode: 'NONE', tagFilter: '*', type: 'GitParameterDefinition')])])
    }
	script {
          if (env.branch == 'origin/feature1') {
		  echo 'I only execute on the feature1 branch'
		  def thisbranch = env.branch
	}
	}
}
