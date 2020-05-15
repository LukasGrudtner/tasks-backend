pipeline {
    agent any
    stages {
        stage ('Inicio') {
            steps {
                TEMP = ${GIT_BRANCH}
                LOCAL_GIT_BRANCH = "${TEMP#*/}"
                echo "Git branch: ${LOCAL_GIT_BRANCH}"
            }
        }
    }
}