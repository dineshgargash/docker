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
                sh 'docker-compose down && docker-compose up -d'
                
            }
        }
    }
    
}

    
    
    

