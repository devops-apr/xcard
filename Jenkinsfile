node('maven-label') {
   def mvnHome
   stage('Preparation') { 
     
      git branch: 'dev', url: 'https://github.com/devops-apr/xcard.git'
      
      mvnHome = tool 'M3'
   }
   stage('Build') {
      
      if (isUnix()) {
         sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean package"
      } else {
         bat(/"${mvnHome}\bin\mvn" -Dmaven.test.failure.ignore clean package/)
      }
   }
   stage('Results') {
      junit '**/target/surefire-reports/TEST-*.xml'
      archiveArtifacts 'target/*.jar'
   }
}
