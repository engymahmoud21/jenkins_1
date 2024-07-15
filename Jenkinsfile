pipeline {
  agent any
    
  stages {
    stage('Check Docker') {
      steps {
          sh '''#!/bin/bash
                    cd /home/Engy/Desktop/Docker-comp
                    if [ "$(docker ps --filter "name=docker-mongo-express-1}" --filter "status=running" -q)" ]; then
                        echo "Express container is already running."
                    else
                        echo "Express container is not running. Starting it up..."
                        docker compose up -d
                    fi'''
			}
      }
    }
  }
