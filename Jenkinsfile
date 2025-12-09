pipeline {
    agent any

    stages {
        stage('Checkout'){
            steps {
              git url: 'https://github.com/SamGleaves2/lbg-vat-calculator.git',
                  branch: 'main'

            }
        }
        stage('Build') {
            steps {
              npm 'install'
              npm 'run build'

           }
        }
        stage('Archive') {
            steps {
              sh 'tar -czf build.tar.gz build'
              archiveArtifacts 'build.tar.gz'
            }
        }
    }
}