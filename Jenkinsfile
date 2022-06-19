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
               pwsh(script: 'docker images -a')
              pwsh(script: """
                cd Angular/
                docker images -a
                docker build -t jenkins-pipeline .
                cd..
                """)
            }
        }
    }
}
