pipeline{
        agent any
        stages{
            stage('Repository'){
                steps{
                     sh "mkdir -p ~/newfolder"
                     sh "mv install-stage.sh ~/newfolder/install-stage.sh"
                     sh "cd ~/newfolder/"    
                     sh "sudo chmod +x ~/newfolder/install-stage.sh"
                }
            }
            stage('Install-Docker'){
                steps{
                    sh "sudo sh . ~/newfolder/.install-stage.sh"
                }
            }

            stage('Deployment'){
                steps{
                     sh "cd ~/jenkins/newfolder/chaperootodo_client"
                     sh "sudo docker-compose up -d"
                    }
               }
        }  
}
