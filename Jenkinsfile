pipeline{
    agent any
    stages{
        stage("Clean Up"){
            steps{
                deleteDir()
            }
        }
        stage("Clone Repo"){
            steps{
                sh "git clone https://github.com/gabrielf/maven-samples.git"
            }
        }
        stage("Build"){
            steps{
                dir("maven-samples")
                sh "mvn clean install"
            }
        }
        stage("Test"){
            steps{
                dir("maven-samples")
                sh "mvn test"
            }
        }
    }
}
