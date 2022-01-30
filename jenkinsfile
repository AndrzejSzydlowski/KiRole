pipeline {
    agent {
        label 'Agent'
    }
    stages {
    stage('repo'){
        steps{
            git credentialsId: '49bba99b-93c4-41a2-9a7b-eb0baf23bb6b', url: 'git@github.com:AndrzejSzydlowski/KiRole.git'
        }
    }
    stage('requirements'){
        steps{
            sh '''pip3 install molecule-docker
            pip3 install -r test-requirements.txt'''
        }
    }
    stage('run molecule'){
        steps{
            sh 'molecule test'
        }
    }
    }
