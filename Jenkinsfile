node("small") 
{ 
  stage ("git-clone") 
  { 
    echo " Launching Medium Instance and cloning GIT "
    checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'rajiv-github', url: 'https://github.com/verma-raj/AshokITProject.git']]]) 
   } 
  
  stage ("Compiling the code"){ 
    echo "**** Compiling the code*****"
    sh 'mvn -v'
    sh 'mvn clean compile'}
	
  stage ("Unit Testing the code"){
    echo "**** Testing the code*****"
    sh 'mvn test'}
	
  stage ("Static Code analysis"){ echo " SonarQube will be done later"}
  
  stage ("Creating Package"){
    echo "**** Packaging the code*****"
    sh 'mvn package'}
	
  stage ("Push Nexus"){
  echo " Pushing to nexus Now "
  nexusArtifactUploader artifacts: [[artifactId: '01-maven-web-app', classifier: '', file: 'target/01-maven-web-app.war', type: 'war']], credentialsId: 'nexus_cred', groupId: 'maven', nexusUrl: '34.226.136.157:8081', nexusVersion: 'nexus2', protocol: 'http', repository: 'devopspractice_snapshot', version: '1.0'
  
  }
   
}
