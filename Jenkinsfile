pipeline{
    agent any 
    stages{
        stage("clone code"){
            steps{
            echo "cloning the code"    
            git branch: 'main', url: 'https://github.com/dineshgargash/docker.git'
            }
        }
        stage("build image"){
            steps{
                echo "build is in progersss"
                sh 'docker build -t rachna .'
                
                
            }
        }
        stage("deploy to docker hub"){
            steps{
                echo "deploy in progress"
                withCredentials([usernamePassword(credentialsId: 'ddt', passwordVariable: 'pwd', usernameVariable: 'uname')]){
                sh "docker tag rachna ${env.uname}/dinesh:latest"
                sh "docker login -u ${env.uname} -p ${env.pwd}"
                sh "docker push ${env.uname}/dinesh:latest"
                }
                sh " docker-compose down && docker-compose up "
                
                
                
                
    }

    }
    }  
}

    
    
    

