pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/Faiza467/my-lamp-app.git'
            }
        }

        stage('Build and Deploy Containers') {
            steps {
                script {
                    sh 'docker-compose -p travel_blog_ci2 -f docker-compose-part2.yml down || true'
                    sh 'docker-compose -p travel_blog_ci2 -f docker-compose-part2.yml build --no-cache'
                    sh 'docker-compose -p travel_blog_ci2 -f docker-compose-part2.yml up -d --remove-orphans'
                }
            }
        }
    }
}
