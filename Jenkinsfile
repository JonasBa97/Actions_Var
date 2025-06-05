pipeline {
  agent any

  environment {
    GLOBAL_VAR = 'global variable'
    MY_SECRET_CREDENTIAL = credentials('JonasBa97')
  }

  stages {
    stage('Globale Variable verwenden') {
      steps {
        echo "GLOBAL_VAR: ${env.GLOBAL_VAR}"
      }
    }

    stage('Lokale Variable testen') {
      environment {
        LOCAL_VAR = 'local variable'
      }
      steps {
        echo "LOCAL_VAR: ${env.LOCAL_VAR}"
        echo "GLOBAL_VAR: ${env.GLOBAL_VAR}"
      }
    }

    stage('Secret verwenden') {
      steps {
        script {
          def secretLength = env.MY_SECRET_CREDENTIAL.length()
          echo "Länge des Secrets: ${secretLength}"
        }
      }
    }
/*
    stage('BONUS: Shell-Skript mit Parametern') {
      steps {
        writeFile file: 'script.sh', text: '''
        #!/bin/bash
        echo "Parameter 1: $1"
        echo "Parameter 2: $2"
        '''
        sh 'chmod +x script.sh'
        sh './script.sh $GLOBAL_VAR $LOCAL_VAR'
      }
    }
*/
  }
}
