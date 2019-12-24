node {
    
 stage('Git checkout'){
	git 'https://github.com/joshiPriya/Helloworld.git'
}

stage('compile-package')
{
    def mvnhome = tool name: 'maven3', type: 'maven'
    sh "${mvnhome}/bin/mvn clean package"

}
 
  stage('SSh-connection'){
        sshPublisher(publishers: [sshPublisherDesc(configName: 'docker_host', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: 'docker stop mywebapp; docker rm -f mywebapp; docker image rm -f mywebapp; docker image rm -f prijo1/mywebapp:v1; cd /home/dockeradmin/docker1;docker build -t mywebapp .;docker tag mywebapp prijo1/mywebapp:v1;', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '//home//dockeradmin//docker1', remoteDirectorySDF: false, removePrefix: 'webapp/target', sourceFiles: 'webapp/target/*.war')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: true)])

    
 }


}
