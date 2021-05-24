 pipeline{

    agent {
        label 'NODEJS'
    }

    stages {

        stage('Download Dependencies') {
            steps {
                sh '''
                 go get -d && go build
            '''
            }
        }
        stage('prepare Artifacts') {
            steps {
                sh '''
                zip -r login.zip *
            '''
            }

        }
        stage('upload Artifacts') {
            steps {
                sh '''
           curl -f -v -u admin:shivark@99 --upload-file login.zip http://172.31.3.191/:8081/repository/login/login.zip
        '''
            }
        }
    }
}