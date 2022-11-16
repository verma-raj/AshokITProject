properties([parameters([choice(choices: ['master\nfeature1\nfeature2'], name: 'Branches')])])

node
{ 
  stage ("git-clone") 
    echo " Pulling changes from branch $(params.branch)
    git url: "https://github.com/verma-raj/AshokITProject.git", branch: "$(params.branch)"
     echo " pipeline completed "
}
