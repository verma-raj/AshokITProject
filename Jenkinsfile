properties([parameters([choice(choices: ['master\nfeature'], name: 'GitBranch')])])
echo "This is the choice $(params.branch)"
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
  sh """mvn -U org.apache.maven.plugins:maven-deploy-plugin:2.8.1:deploy-file -DgroupId=in.ashokit \
  -DartifactId=01-maven-web-app \
  -Dversion=1.0-SNAPSHOT \
  -Dpackaging=war \
  -Dfile=target/01-maven-web-app.war \
  -DrepositoryId=devopspractice_snapshot \
  -Durl=http://34.226.136.157:8081/nexus/content/repositories/devopspractice_snapshot/"""
  
  }
   
}
