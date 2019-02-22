def do_it = {
    sh 'id | tee out/out.txt'
    sh 'date | tee -a out/out.txt'
}
pipeline {
    agent none
    stages {
        stage("build"){
            agent {
                docker "python:3.7"
            }
            steps {
                script {do_it()}
                archiveArtefacts artifacts: 'out/', onlyIfSuccessful:true
            }
        }
    }
}

