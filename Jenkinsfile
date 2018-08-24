node('docker') {

    stage('Checkout') {
        checkout scm
    }

    stage('Build doc') {
        def hugo = docker.build("hugo:${env.BUILD_ID}")

        hugo.inside {
            sh 'cp -a /usr/share/nginx/html ./doc-container/'
        }
    }

    stage('Build container') {
        def homepage = docker.build("doc:${env.BUILD_ID}", "./doc-container")
        stage('Push container') {
            docker.withRegistry('https://docker-registry.in.pascom.net', '6495aa9c-a076-4ac9-89eb-a29f622667f6') {

                homepage.push()
                homepage.push('latest')
            }
        }

    }

}