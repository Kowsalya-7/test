pipeline{
    agent any
    triggers{
        githubPush()
    }
    tools{
        maven 'Maven'
    }
    stages{
        stage('github validation'){
          steps{
                 git branch: 'main', url: 'https://github.com/Kowsalya-7/test.git'
          }
        }
        stage('compiling the code'){
          steps{
                 sh 'mvn compile'
          }
        }
        stage('testing the code'){
            steps{
                sh 'mvn test'
            }
        }
        stage('package'){
            steps{
                sh 'mvn package'
            }
        }
        stage("deploy the project on tomcat"){
            steps{
                sh "sudo /bin/mv /var/lib/jenkins/workspace/pipeline/target/addressbook.war /home/ubuntu/apache-tomcat-8.5.100/webapps/"
            }
        }
    }
}
