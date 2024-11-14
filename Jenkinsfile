@Library('shared')_
pipeline{
    agent { label 'ahk'}
    
    stages{
        stage("Code clone"){
            steps{
                
            clone("https://github.com/ahk1022/django-notes-app.git","main")
            }
        }
        stage("Code Build"){
            steps{
            docker_build("notes-app","latest","ahk3983")
            }
        }
        stage("Push to DockerHub"){
            steps{
                docker_push("DockerHubCreds","notes-app","latest","ahk3983")
            }
        }
        stage("Deploy"){
            steps{
                deploy()
            }
        }
        
    }
}
