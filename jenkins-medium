node("medium") 
{ 
  stage ("git-clone") 
  echo " Launching Medium Instance and cloning GIT "
    { checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'rajiv-github', url: 'https://github.com/verma-raj/AshokITProject.git']]]) } 
    
   
}
