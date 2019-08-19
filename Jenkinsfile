node {
   // Mark the code checkout 'stage'....
   stage 'Checkout'
   
   git url: 'https://github.com/manikarnam/docker12.git'

   // Get the maven tool.
   // ** NOTE: This 'M3' maven tool must be configured
   // **       in the global configuration.           
   def mvnHome = tool 'M3'

   // Mark the code build 'stage'....
   stage 'Build'
   // Run the maven build
   sh "${mvnHome}/bin/mvn -Dmaven.test.failure.ignore clean install "
   //step([$class: 'JUnitResultArchiver', testResults: '**/target/surefire-reports/TEST-*.xml'])
   stage 'success'
   echo 'successfully deployed'
   stage 'deploy'
  // sh '/mani/target/mani.war TOMCAT_DIRECTORY/webapps/'
   deploy adapters: [tomcat8(credentialsId: '1c3e621e-a275-4c07-a745-aa3e688ca1b5', path: '', url: 'http://http://192.168.228.130:9090')], contextPath: 'mani.war', war: 'jenkins-pipe3/target/mani.war'
}
   
