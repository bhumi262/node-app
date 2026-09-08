@Library('my-shared-library') _

pipeline {

    agent any

    stages {

        stage('Clone') {
            steps {
                cloneRepo('https://github.com/bhumi262/node-app.git', 'main')
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    def installer = new org.example.NodeDependencyInstaller(this)
                    installer.install()
                }
            }
        }

        stage('Test') {
            steps {
                runTests('npm test')
            }
        }
    }
}