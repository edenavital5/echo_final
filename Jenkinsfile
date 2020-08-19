// def version="\$(./calculate.sh)"
pipeline {
    agent any

    // triggers {
    //     github(
    //         triggerOnPush: true,
    //         triggerOnMergeRequest: true,
    //         branchFilterType: 'All',
    //         addVoteOnMergeRequest: true)
    // }
    stages { 
        stage('build') {
            steps {
                script {
                    if (env.BRANCH_NAME == 'master') {
                        sh "docker build -t 1.0.${BUILD_NUMBER} ."
                    } else {
                        sh "docker build -t dev-${GIT_COMMIT_HASH} ."
                    }
                }
            }
        }


        // stage('build') {
        //     when {
        //         expression { BRANCH_NAME =~ /^(master$)/}
        //     }
        //     steps{
        //         script{
        //             sh "docker build -t 1.0.${BUILD_NUMBER} ."
        //         }
        //     }
        //     when {
        //         expression { BRANCH_NAME =~ /^(dev$)/}
        //     }
        //     steps{
        //         script{
        //             sh "docker build -t dev-${GIT_COMMIT_HASH} ."
        //         }
        //     }
        //     when {
        //         expression { BRANCH_NAME =~ /^(staging$)/}
        //     }
        //     steps{
        //         script{
        //             sh "docker build -t staging-${GIT_COMMIT_HASH} ."
        //         }
        //     }
        // }
    }
}