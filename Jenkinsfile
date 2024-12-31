pipeline {
    agent any
    tools {
        maven 'MAVEN_3.9.9'
    }
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('VCS') {
            steps {
                git url: 'https://github.com/shalu-233/multi-branch-dummy.git',
                branch: 'main'
            }
        }
        stage('build') {
            steps {
                sh 'echo building code....'
                sh 'echo static code analysis'
                sh 'echo archive the package into jfrog'
                sh 'echo quality gate'
            }
    
        }
        stage('deploy') {
            steps {
                sh 'echo deploy to production'
                sh 'echo disply results'
            }
        }

    }
        
}