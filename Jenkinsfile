node{
    def mvnHome
 
   stage('SetEnv') { 
      git 'https://github.com/VysaliKamatham96/synkrepository.git'
      mvnHome = tool 'MAVEN_HOME'
	   
   }
   
   stage('CompileandPackage') {
      withEnv(["MVN_HOME=$mvnHome"]) {
            bat(/"%MVN_HOME%\bin\mvn" -Dmaven.test.failure.ignore clean compile/)
         }
      
   }
   stage('Snyk'){
        snykSecurity failOnIssues: false, organisation: '9827b06b-22ac-4940-b3f3-3615f1bacd2c', snykInstallation: 'MySnyk', snykTokenId: 'mysnyk_key'
       
   }

}
