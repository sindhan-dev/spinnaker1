node {   
 

    stage('Checkout the dockefile from GitHub') {            
      git branch: 'main', url: 'https://github.com/sindhan-dev/spinnaker1.git'        
    }
     
    stage('Build the Image and Push to Docker hub') {                
      app = docker.build('sindhans/demo')                
      withDockerRegistry([credentialsId: 'docker']) {                
      app.push("${env.BUILD_NUMBER}")                
      app.push('latest')
     }        
    }    

   
}

