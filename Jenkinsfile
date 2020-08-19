pipeline {
    agent any

    stages { 
        stage('build') {
            steps {
                script {
                    if (env.BRANCH_NAME == 'master') {
                        sh "docker build -t 1.0.${BUILD_NUMBER} ."
                    } else if (env.BRANCH_NAME == 'dev'){
                        sh "docker build -t dev-${GIT_COMMIT} ."
                    } else if (env.BRANCH_NAME == 'staging'){
                        sh "docker build -t staging-${GIT_COMMIT} ."
                    }
                }
            }
        }

        stage('deploy') {
            steps{
                script{
                  withCredentials([[$class: 'UsernamePasswordMultiBinding',credentialsId: 'dockerhub',usernameVariable: 'USER',passwordVariable: 'PASSWORD']]){
                  sh "docker login -u $USER -p $PASSWORD"
                  if (env.BRANCH_NAME == 'master') {
                        sh "docker push edenavital/echo-app:1.0.${BUILD_NUMBER}"
                    } else if (env.BRANCH_NAME == 'dev'){
                        sh "docker push edenavital/echo-app:dev-${GIT_COMMIT}"
                    } else if (env.BRANCH_NAME == 'staging'){
                        sh "docker push edenavital/echo-app:staging-${GIT_COMMIT}"
                    }
                }
            }
        }


    }
}