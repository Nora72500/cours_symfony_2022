pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo 'stage:Build'
        bat 'composer install'
      }
    }

    stage('test') {
      parallel {
        stage('unitaire') {
          steps {
            bat 'php bin/phpunit tests/unit'
          }
        }

        stage('integration') {
          steps {
            bat 'php bin/phpunit tests/unit'
          }
        }

        stage('fonctionnel') {
          steps {
            bat 'php bin/phpunit tests/unit'
          }
        }

      }
    }

    stage('deploy') {
      steps {
        bat 'symfony server:start'
      }
    }

  }
}