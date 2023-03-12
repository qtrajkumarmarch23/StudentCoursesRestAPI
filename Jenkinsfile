pipeline {
    agent { label 'JDK_8' }
    triggers {
        pollSCM('* * * * *')
    }    
    stages {
        stage('vcs') {
            git url: 'https://github.com/qtrajkumarmarch23/StudentCoursesRestAPI.git'
                branch: 'develop'
        }
        stage('build') {
            steps {
                sh 'docker image build -t rajkumar207/spc:latest .'
            }
        }
        stage('scan and push') {
            steps {
                sh 'echo docker scan rajkumar207/spc:latest'
                sh 'docker image push rajkumar207/spc:latest'
            }    
        }          
    }
}