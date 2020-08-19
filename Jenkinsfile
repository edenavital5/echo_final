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
            steps{
                script{
                        sh "echo hello"
                    }
                }
            }
        // stage('build_master') {
        //     when {
        //         expression { BRANCH_NAME =~ /^(master)/}
        //     }
        //     steps{
        //         configFileProvider(
        //         [configFile(fileId: 'settings', variable: 'MAVEN_SETTINGS')]) {
        //         sh "mvn versions:set -DnewVersion=1.0-SNAPSHOT"
        //         sh "mvn -s $MAVEN_SETTINGS clean deploy"
        //         }
        //     }
        // }
        // stage('build_release') {
        //     when {
        //         expression { BRANCH_NAME =~ /^(release\*)/}
        //     }
        //     steps{
        //         sh "chmod 700 ./calculate.sh"
        //         configFileProvider(
        //         [configFile(fileId: 'settings', variable: 'MAVEN_SETTINGS')]) {
        //         sh "mvn versions:set -DnewVersion=$version"
        //         sh "mvn -s $MAVEN_SETTINGS clean deploy"
        //         }
        //     }
        // }
        // stage('build_else') {
        //     when {
        //         not{
        //             expression { BRANCH_NAME =~ /^(master)/}
        //         }
        //         not{
        //             expression { BRANCH_NAME =~ /^(release\*)/}
        //         }
        //     }
        //     steps{
        //         sh "mvn clean install"
        //     }
        // }
    }
}