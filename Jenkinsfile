pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'rm -rf build'
                sh 'mkdir build'
                sh 'touch build/traveler.txt'
                sh 'echo "Job Interview at Travelers Ins. with the below names:" >> build/traveler.txt'
                sh 'echo "Gregory Richmond" >> build/traveler.txt'
                sh 'echo "George Sadej" >> build/traveler.txt'
                sh 'echo "Nirav Pravasi" >> build/traveler.txt'
                sh 'echo "Dan Hecker" >> build/traveler.txt'
                sh 'echo "Bob Barrow" >> build/traveler.txt'
                sh 'echo "Oswald Cline-Cole" >> build/traveler.txt'
                
            }
        }
        stage('Test') {
            steps {
                sh 'test  -f build/traveler.txt'
                sh 'grep "Gregory Richmond" build/traveler.txt'
                sh 'grep "George Sadej" build/traveler.txt'
                sh 'grep "Nirav Pravasi" build/traveler.txt'
                sh 'grep "Dan Hecker" build/traveler.txt'
                sh 'grep "Bob Barrow" build/traveler.txt'
                sh 'grep "Oswald Cline-Cole" build/traveler.txt'
            }
        }
        stage('Publish') {
            steps {
                archiveArtifacts artifacts: 'build/'
            }
        }
    }
}
