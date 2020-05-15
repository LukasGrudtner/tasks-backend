pipeline {
    agent any
    stages {
        stage ('Início') {
            steps {
                LOCAL_GIT_BRANCH = ${GIT_BRANCH#*/}
                echo "Git branch: ${GIT_BRANCH#*/}"
            }
        }
    }
}