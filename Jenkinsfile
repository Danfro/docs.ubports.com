def do_it = {
    sh 'id' > out.txt
    sh 'date' >> out.txt
}
pipeline {
    agent {
        docker "python3.5"
    }
    stages {
        stage("build"){
            steps {
                script {do_it()}
            }
        }
    }
}

