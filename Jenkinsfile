pipeline{
        agent any
        stages{
            stage('Repository'){
                steps{
                     sh "mkdir ~/newfolder"
                     sh "mv install-stage.sh ~/new/install-stage.sh"
                     sh "cd ~/new/"    
                     sh "sudo chmod +x ~/new/install-stage.sh"
                     sh "git clone https://gitlab.com/qacdevops/chaperootodo_client"
                }
            }
            stage('Install-Docker'){
                steps{
                    sh ". ~/newfolder/.install-stage.sh"
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
