@Library('jenkins-shared-library@master') _

pipeline{
    agent any
    stages{
        stage("Set variables"){
            steps{
                script {
                    env.VERSION = new Date().format("yy.MM.dd-HH.mm", TimeZone.getTimeZone('UTC'))
                    env.DOCKER_IMAGE = "mikhaild/${JOB_NAME}:${VERSION}"
                    currentBuild.description = "Image tagged as ${VERSION}"
                }
            }
        }
        stage("Build dockerImage"){
            steps{
                script{
                    sh '''
                        docker build \
                            -f Dockerfile \
                            -t ${DOCKER_IMAGE} .
                        docker push ${DOCKER_IMAGE}
                    '''
                }
            }
        }
    }
}
