def imageName = 'oleksiihead/films-store'

node('workers') {
    stage('Checkout SCM'){
        checkout scm
    }

    def imageTest = docker.build("${imageName}-test", "-f Dockerfile.test .")

    stage('Quality Tests'){
        imageTest.inside{
            sh 'npm run lint'
        }
    }
}
