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
                sh 'building code ....'
                sh 'static code analysis'
                sh 'archive the package into jfrog'
                sh 'quality gate'
            }
    
        }
        stage('deploy') {
            steps {
                sh 'usign terraform create env'
                sh 'use kubectl to deploy'
                sh 'run end to end system tests'
            }
        }
        stage('test') {
            steps {
                sh 'run end to end system tests'
                sh 'display test results'
            }
        }
    }
}