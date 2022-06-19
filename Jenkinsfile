pipeline {
    agent any

    stages {
        stage('Verify Branch') {
            steps {
                echo "$GIT_BRANCH"
            }
        }
          stage('Docker Build') {
            steps {
               sh(script: 'docker images -a')
              sh(script: """
                cd src/
                docker images -a
                docker build -t jenkins/jenkins:lts
                cd..
                """)
            }

        }
    }
}
