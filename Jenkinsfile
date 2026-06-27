pipeline {
    agent any
    stages {
        stage('Docker Check') {
            steps {
                sh 'docker --version'
            }
        }
        stage('Build Image') {
            steps {
                sh '''
                    mkdir -p /tmp/myapp
                    cat > /tmp/myapp/Dockerfile << EOF
FROM python:3.11-slim
WORKDIR /app
RUN echo 'print("Hello from Jenkins!")' > app.py
CMD ["python", "app.py"]
EOF
                    docker build -t my-app-jenkins:${BUILD_NUMBER} /tmp/myapp
                '''
            }
        }
        stage('Verify') {
            steps {
                sh 'docker images my-app-jenkins'
            }
        }
    }
}