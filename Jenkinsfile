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
            dockerbuild("notes-app","latest")
            }
        }
        stage("Push to DockerHub"){
            steps{
                dockerpush("DockerHubCreds","notes-app","latest")
            }
        }
        stage("Deploy"){
            steps{
                deploy()
            }
        }
        
    }
}
