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
                     sh "sudo docker-compose down"
                     sh "sudo docker-compose build"
                     sh "sudo docker-compose up -d"
                    }
               }
        }  
}
