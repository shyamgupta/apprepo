pipeline{
    agent any
    stages{
        stage('checkout'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/shyamgupta/apprepo.git']]])
            }
        }
        stage('build and push image to ecr'){
        steps{
            sh '''docker build -t sgecr .
        docker tag sgecr:latest 692247192354.dkr.ecr.us-east-1.amazonaws.com/sgecr:latest
        docker push 692247192354.dkr.ecr.us-east-1.amazonaws.com/sgecr:latest'''
        }
    }
    }
    
    
}
