pipeline {
    agent any
    stages{
        stage('Build'){
            steps {
                sh 'mvn clean package'
                sh 'pwd'
                sh 'whoami'
                sh "docker build -t webapp:${env.BUILD_ID} ."
                sh 'docker login -u grandhisaiteja -p Sai@1696'
                sh "docker tag webapp:${env.BUILD_ID} grandhisaiteja/webapp:${env.BUILD_ID}"
                sh "docker push grandhisaiteja/webapp:${env.BUILD_ID}"
            }
        }
    }
}
