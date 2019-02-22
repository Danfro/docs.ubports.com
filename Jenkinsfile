def do_it = {
    sh 'id | tee out.txt'
    sh 'date | tee -a out.txt'
}
pipeline {
    agent none
    stages {
        stage("build"){
            agent {
                docker "python:3.6"
            }
            steps {
                script {do_it()}
            }
        }
    }
}

