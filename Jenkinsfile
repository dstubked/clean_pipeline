node {
    def app

    stage('Clone repository') {
        /* Clone repository to workspace */

        checkout scm
    }

    stage('Build image') {
        /* This builds the actual image */

        app = docker.build("dstubked/docker-test")
    }
    
    stage ('Aqua Microscanner') {
        aquaMicroscanner imageName: 'dstubked/docker-test', notCompliesCmd: '', onDisallowed: 'fail', outputFormat: 'html'
    }
    
    
    /*stage('Push image') { */
        /* Finally, we'll push the image with two tags:
         * First, the incremental build number from Jenkins
         * Second, the 'latest' tag.
         */
        /*docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")*/
}
