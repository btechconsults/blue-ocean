pipeline {
  agent any
  stages {
    stage('Fetch code') {
      parallel {
        stage('Fetch code') {
          steps {
            node(label: 'jenkins master') {
              git(url: 'https://github.com/btechconsults/blue-ocean.git', branch: 'main', changelog: true, poll: true)
            }

          }
        }

        stage('error') {
          steps {
            git(url: 'https://github.com/btechconsults/blue-ocean.git', branch: 'main')
          }
        }

      }
    }

    stage('install Apache server') {
      steps {
        sh 'echo "install apache2 server"'
      }
    }

    stage('Deploy WebApp') {
      steps {
        sh 'cp -R * /var/www/html/'
      }
    }

  }
}