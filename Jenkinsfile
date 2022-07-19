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
        stage("Last"){
            steps {
                echo "Completed!!!"
            }
        }
         stage("Python Script Execution"){
            steps {
                dir("/var/lib/jenkins/workspace/first_project")
                sh "mv /var/lib/jenkins/workspace/test.py /var/lib/jenkins/workspace/first_project/test.py"
                sh "python hello.py"
            }
        }
    }
}
