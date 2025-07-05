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
            archiveArtifacts artifacts: 'C:/Users/madhu/AppData/Local/Docker/wsl/Docker/Framework/14Framework/output/flight/emailable-report.html', followSymlinks: false
            archiveArtifacts artifacts: 'C:/Users/madhu/AppData/Local/Docker/wsl/Docker/Framework/14Framework/output/vendor/emailable-report.html', followSymlinks: false
        }
    }
}