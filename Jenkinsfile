pipeline {
    agent { label 'docker_77' }
    triggers {
        pollSCM ('* * * * *')
    }
    stages{
        stage ('vcs') {
            steps {
                gti url: 'https://github.com/dimplevayigandla1005/StudentCoursesRestAPI.git'
                 branch: 'master'
            }
        }
        stage ('build') {
            steps {
                sh 'docker image build -t dimplevayigandla1005/space:latest .'
            }
        }
        stage ('scan and push') {
            steps {
                sh 'echo docker scan dimplevayigandla1005/space:latest'
                sh 'docker image push dimplevayigandla1005/space:latest'
            }
        }
    }
}