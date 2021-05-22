pipeline { 
    agent {
        label 'NODEJS'
    } 

    stages {
        
     stage('Download Dependencies') {

         steps {
             sh '''
               export GOPATH=/home/ubuntu/go && export GOBIN=$GOPATH/bin && go get && go build
                 '''
         }

     }
     stage('Prepare Artifacts') {
       steps {
         sh '''
           
           zip -r login.zip *
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

