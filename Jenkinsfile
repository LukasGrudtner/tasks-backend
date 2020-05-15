pipeline {
    agent any
    stages {
        stage ('Inicio') {
            steps {
                LOCAL_GIT_BRANCH = "${GIT_BRANCH#*/}"
                echo "Git branch: ${LOCAL_GIT_BRANCH}"
            }
        }
    }
}