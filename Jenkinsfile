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
    }
}