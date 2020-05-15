pipeline {
    agent any
    stages {
        stage ('Início') {
            steps {
                LOCAL_GIT_BRANCH = "${GIT_BRANCH#*/}"
                echo "Git branch: ${LOCAL_GIT_BRANCH}"
            }
        }
    }
}