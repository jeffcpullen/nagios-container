#!groovy

// https://github.com/feedhenry/fh-pipeline-library
@Library('fh-pipeline-library') _

stage('Trust') {
    enforceTrustedApproval()
}

final String COMPONENT = "nagios4"
final String VERSION = "4.0.8"
final String DOCKER_HUB_ORG = "rhmap"
final String DOCKER_HUB_REPO = COMPONENT

fhBuildNode(['label': 'openshift']) {

    stage('Build Image') {
        dockerBinaryBuild(COMPONENT, VERSION, DOCKER_HUB_ORG, DOCKER_HUB_REPO, 'dockerhubjenkins', '.')
    }

}
