def install_dependencies = {
    sh 'pip install --user --target mypip --no-cache-dir -r requirements.txt'
}
def build_docs = {
    sh 'pipenv run sphinx-build -Wab html . _build/html/'
}
def just_build_it_already = {
    sh './build.sh'
}
pipeline {
    agent none
    stages {
        stage("build"){
            agent {
                docker "python:3.7"
            }
            steps {
                script {install_dependencies()}
                script {just_build_it_already()}
                archiveArtifacts artifacts: 'docs/_build/html/', onlyIfSuccessful: true
                deleteDir()
            }
        }
    }
}

