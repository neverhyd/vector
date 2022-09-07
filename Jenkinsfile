pipeline {
    agent {
        label 'centos'
    }

    stages {
        stage('Git') {
            steps {
                git branch: 'main', url: 'https://github.com/neverhyd/vector.git'
            }
        }
        stage('Galaxy') {
            steps{
                sh "ansible-galaxy install -r requirements.yml"
            }
        }
        stage('molecule'){
            steps{
                sh "molecule test -s ubuntu"
        }
        }
    }
}