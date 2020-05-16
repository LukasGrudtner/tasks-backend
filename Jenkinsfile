pipeline {
    agent any
    stages {
        stage ('Build Backend') {
            steps {
                bat 'mvn clean package -DskipTests=true'
            }
        }
        stage ('Unit Tests') {
            steps {
                bat 'mvn test'
            }
        }
        stage ('Sonar Analysis') {
            environment {
                scannerHome = tool 'SONAR_SCANNER'
            }
            if (${GIT_BRANCH} == 'master' || ${GIT_BRANCH} == 'origin/master') {
                steps {
                    withSonarQubeEnv('SONAR_LOCAL') {
                        bat "${scannerHome}/bin/sonar-scanner -e -Dsonar.projectKey=DeployBack -Dsonar.host.url=http://localhost:9000 -Dsonar.login=6ef2c40c4db531cbe6290829d6587637c27f93bf -Dsonar.java.binaries=target -Dsonar.coverage.exclusions=**/.mvn/**,**/src/test/**,**/model/**,**Application.java"
                    }
                }
            } else {
                steps {
                    withSonarQubeEnv('SONAR_LOCAL') {
                        bat "${scannerHome}/bin/sonar-scanner -e -Dsonar.branch.name=${GIT_BRANCH} -Dsonar.projectKey=DeployBack -Dsonar.host.url=http://localhost:9000 -Dsonar.login=6ef2c40c4db531cbe6290829d6587637c27f93bf -Dsonar.java.binaries=target -Dsonar.coverage.exclusions=**/.mvn/**,**/src/test/**,**/model/**,**Application.java"
                    }
                }
            }
            
        }
    }
    
}