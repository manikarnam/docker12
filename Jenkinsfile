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
   sh "${mvnHome}/bin/mvn -Dmaven.test.failure.ignore clean install package "
   //step([$class: 'JUnitResultArchiver', testResults: '**/target/surefire-reports/TEST-*.xml'])
   stage 'success'
   echo 'successfully deployed'
   stage 'deploy'
   echo 'tomcat deployment started'
 
   //deploy adapters: [tomcat7(credentialsId: 'tomcatmanager', path: '', url: 'http://172.17.1.86:9090')], contextPath: null, onFailure: false, war: '**/*.war'
}
   
