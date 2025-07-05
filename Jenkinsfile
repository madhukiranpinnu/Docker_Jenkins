pipeline{
    agent any
    stages{
        stage("grid up"){
            steps{
                bat "docker-compose -f grid.yaml up -d"
            }
        }
        stage("test-suite up"){
            steps{
                bat "docker-compose -f testsuites.yaml up"
            }
        }
    }
    post{
        always{
            bat "docker-compose -f grid.yaml down"
            bat "docker-compose -f testsuites.yaml down"
             archiveArtifacts artifacts: '/output/flight/emailable-report.html', followSymlinks: false
            archiveArtifacts artifacts: '/output/vendor/emailable-report.html', followSymlinks: false
        }
    }
}