pipeline {
     agent any
     stages {
         stage('Build') {
             steps {
                 sh 'echo "Hello World"'
                 sh '''
                     echo "Multiline shell steps works too"
                     ls -lah
                 '''
             }
         }      
         stage('Upload to AWS') {
              steps {
                  withAWS(region:'us-west-1',credentials:'Jenkins-cred') {
                  sh 'echo "Uploading content with AWS creds"'
                      s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'index.html', bucket:'mycloudiness.com')
                         s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'components.html', bucket:'mycloudiness.com')
                       s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'main.bc58148c.js.gz', bucket:'mycloudiness.com')
                       s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'assets', bucket:'mycloudiness.com')
                       s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'sample', bucket:'mycloudiness.com')
                       s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'main.bc58148c.js', bucket:'mycloudiness.com')
                       s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'main.bc58148c.map', bucket:'mycloudiness.com')
                       s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'main.d8e0d294.css', bucket:'mycloudiness.com')
                       s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'main.d8e0d294.css.gz', bucket:'mycloudiness.com')
                       
                     
                  }
              }
         }
     }
}
