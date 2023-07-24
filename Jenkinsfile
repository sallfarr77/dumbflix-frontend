def branch = "master"
def remote = "origin"
def directory = "~/dumbflix-frontend"
def server = "sallfarrwork@34.28.11.93"
def cred = "dumbflix"

pipeline{
    agent any
    stages{
        stage('repo pull'){
            steps{
                sshagent(credentials: [cred]){
                    script{
                        ssh "ssh -o StrictHostKeyChecking=no ${server} << EOF\n" +
                            "cd ${directory}\n" +
                            "git pull ${remote} ${branch}\n" +
                            "exit\n" +
                            "EOF"
                    }
                }
            }
        }
    }
}
 
