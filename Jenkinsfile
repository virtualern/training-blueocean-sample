pipeline {
  agent {
    docker {
      image 'bitwiseman/training-blueocean-sample'
      args '-u root -v $HOME/.m2:/root/.m2'
    }
    
  }
  stages {
    stage('Build') {
      steps {
        sh '''set -x 
echo "Hello World!"
echo
ls -la
./jenkins/build.sh
'''
      }
    }
    stage('Archive the artifacts') {
      steps {
        archiveArtifacts 'target/*.war'
      }
    }
  }
}