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
                git url: '://github.com/spring-projects/spring-petclinic.git',
                branch: 'main'
            }
        }
        stage('build') {
            steps {
                sh 'echo building code ....'
                sh 'echo static code analysis'
                sh 'echo archive the package into jfrog'
                sh 'echo quality gate'
            }
    
        }
        stage('deploy') {
            steps {
                sh 'echo usign terraform create env'
                sh 'echo run end to end system tests'
            }
        }
        stage('test') {
            steps {
                sh 'echo run end to end system tests'
                sh 'echo display test results'
            }
        }
    }
}