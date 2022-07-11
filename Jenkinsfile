pipeline {
    agent any
    stages {
        stage("Clean Up"){
            steps {
                deleteDir()
            }
        }
        stage("Clone Repo"){
            steps {
                sh "git clone https://github.com/javaparser/javasymbolsolver-maven-sample.git"
            }
        }
        stage("Build"){
            steps {
                dir("javasymbolsolver-maven-sample") {
                    sh "mvn clean install"
                }
            }
        }
        stage("Test"){
            steps {
                dir("javasymbolsolver-maven-sample") {
                    sh "mvn test"
                }
            }
        }
    }
}
