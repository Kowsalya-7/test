pipeline{
    agent any
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
        stage('Deploy to Tomcat using Ansible') {
            steps {
                sh 'ansible-playbook -i inventory.ini deploy.yml'
            }
        }
    }
}
