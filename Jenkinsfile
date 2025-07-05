pipeline{
    agent any
    stages{
        stage("image up"){
            steps{
                bat "docker-compose up"
            }
        }
        stage("image down"){
            steps{
                bat "docker-compose down"
            }
        }
    }
}