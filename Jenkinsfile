pipeline { 
    agent {
        label 'NODEJS'
    } 

    stages {
        
     stage('Download Dependencies') {

         steps {
             sh '''
               npm install
                 '''
         }

     }
     stage('Prepare Artifacts') {
       steps {
         sh '''
           cd static
           zip -r login.zip node_modules server.js
           '''
       }
     }
      stage('Upload Artifacts') {
        steps {
          sh '''
            curl -f -v -u admin:shivark@99 --upload-file login.zip http://172.31.3.191:8081/repository/login/login.zip
            '''
      }
    }
  } 
}

