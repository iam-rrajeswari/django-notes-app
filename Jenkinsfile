@Library('Shared') _
pipeline {
    
    agent { label 'sri' }

    stages {
        
        stage("Hello"){
            steps{
                script {
                    hello()
                }
            }
        }
        stage("code") {
            steps{
                script{
               
                 clone("https://github.com/iam-rrajeswari/django-notes-app.git", "main")
                }
            
             
            }
        }
        stage("build"){
            steps{
                script{
                    docker_build("notes-app","latest","rajeswari2702")
                }
                
            }
            
        }
        stage("push to dockerHub"){
            steps{
                script{
                    docker_push("notes-app","latest","rajeswari2702")
                
                }
            }
        }
        stage("deploy"){
            steps{
                echo "This is deploy stage"
                sh "docker compose up -d"
            }
        }

    }
}

