pipeline{
    agent any 
    environment{
        image2="sample_game"
        tag2="latest"
    }
    stages{
        stage("Build the images "){
            steps{
                script{
                echo "========executing A========"
                withCredentials([usernamePassword(credentialsId: 'dockerhub', passwordVariable: 'PASS', usernameVariable: 'USER')]) {
                sh "docker build -t ${image2}:${tag2} ."
                sh 'echo $USER'
                sh "echo $PASS | docker login -u $USER --password-stdin"
                sh "docker tag ${image2}:${tag2} $USER/${image2}:${tag2}"
                sh "docker push $USER/${image2}:${tag2}"
                }                
            }
                }
            }
            }
        
    }

    
    
