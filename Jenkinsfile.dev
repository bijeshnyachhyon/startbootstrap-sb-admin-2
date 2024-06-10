pipeline {
    agent any

    stages {
        stage('Code fetch') {
            steps {
                echo 'Clone code from Github'
                git url:'https://github.com/bijeshnyachhyon/startbootstrap-sb-admin-2.git', branch: 'master'
            }
        }
        
        stage('Build') {
            steps {
                sh 'docker build -t bijesh-jenkins-build-website .'
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploy on container'
				sh 'docker run -d -p 80:80 bijesh-jenkins-build-website'
            }
        }
    }
}
