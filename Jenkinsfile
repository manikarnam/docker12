node {
   
   stage 'Checkout'
   
   git url: 'https://github.com/manikarnam/docker12.git'
   
   def mvnHome = tool 'M3'
   
   stage 'Build'
   
   sh "${mvnHome}/bin/mvn -Dmaven.test.failure.ignore clean install package "
    
   stage 'success'
   
   echo 'successfully deployed'
   
   stage 'deploy'
   
   echo 'tomcat deployment started'
 
   //deploy adapters: [tomcat7(credentialsId: 'tomcatmanager', path: '', url: 'http://172.17.1.86:9090')], contextPath: null, onFailure: false, war: '**/*.war'
}
   
