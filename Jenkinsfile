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
  // sh '/mani/target/mani.war TOMCAT_DIRECTORY/webapps/'
  // deploy adapters: [tomcat8(credentialsId: '1c3e621e-a275-4c07-a745-aa3e688ca1b5', path: '', url: 'http://http://192.168.228.130:9090')], war: '/target/mani.war'
  // deploy adapters: [tomcat8(credentialsId: '3e07da6c-df95-49d3-beca-de7eee35fd82', path: '', url: 'https://http://192.168.228.130:9090')], contextPath: null, war: '/target/mani.war'
   //deploy adapters: [tomcat8(credentialsId: '3e07da6c-df95-49d3-beca-de7eee35fd82', path: '', url: 'https://192.168.228.130:9090')], contextPath: null, war: '**/*.war'
   //deploy adapters: [tomcat8(credentialsId: '3e07da6c-df95-49d3-beca-de7eee35fd82', path: '', url: 'https://192.168.228.130:9090')], contextPath: null, war: '**/target/mani.war'
   //deploy adapters: [tomcat8(credentialsId: '3e07da6c-df95-49d3-beca-de7eee35fd82', path: '', url: 'http://192.168.228.130:9090')], contextPath: null, onFailure: false, war: '**/*.war'
   //deploy adapters: [tomcat7(credentialsId: 'tomcatmanager', path: '', url: 'http://172.17.1.86:9090')], contextPath: null, onFailure: false, war: '**/*.war'
}
   
