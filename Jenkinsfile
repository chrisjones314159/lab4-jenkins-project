pipeline {
  agent agent
  stages {
    stage('Cleanup') {
      steps {
        sh "sh cleanup.sh || true"
      }
    }

    stage('Buils the Node image') {
      steps {
        sh "docker build -t node .  --no-cache"
      }  
    }
    stage('Run the container') {
      steps {
        sh "docker run -d -p 5000:5000 --name node node"
      }
    }
  }
}
