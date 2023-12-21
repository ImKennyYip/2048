pipeline{
    agent any 
    environment{
        image2="python-argocd-task"
        tag2="1.0"
        version='1.1'
        targetPort='5004'
        containerPort='5004'
    }
    stages{
        stage("hello")
        {
            steps
            {
                checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'git-webhook', url: 'https://github.com/ShekharRedd/game_project']])
            }
        }
        // stage("Pull the latest code from task-management")
        // {
        //     steps{1
        //         script{
        //             sh "git clone https://github.com/ShekharRedd/task_management.git"
        //             dir('/var/jenkins_home/workspace/sample-argocd-pipeline/task_management')
        //             {
        //                 withCredentials([usernamePassword(credentialsId: 'dockerhub', passwordVariable: 'PASS', usernameVariable: 'USER')]) {
        //                 sh "docker build -t ${image2}:${tag2} ."
        //                 sh 'echo $USER'
        //                 sh "echo $PASS | docker login -u $USER --password-stdin"
        //                 sh "docker tag ${image2}:${tag2} $USER/${image2}:${tag2}"
        //                 sh "docker push $USER/${image2}:${tag2}"
        //                 }    
        //             }
        //         }
        //     }
        // }

        stage("update the image version in game-project-repo")
        {
            if(fileExists('game_project')){
                sh "git pull"

            }
            
        }
        }
        
    }

 


 // stage("Building image MASTER"){
        //     // when{
        //     //     expression{

        //     //     }
        //     // }
        //     steps{
        //         script{
        //         echo "========executing A========"
                // withCredentials([usernamePassword(credentialsId: 'dockerhub', passwordVariable: 'PASS', usernameVariable: 'USER')]) {
                // sh "docker build -t ${image2}:${tag2} ."
                // sh 'echo $USER'
                // sh "echo $PASS | docker login -u $USER --password-stdin"
                // sh "docker tag ${image2}:${tag2} $USER/${image2}:${tag2}"
                // sh "docker push $USER/${image2}:${tag2}"
                // }                
        //     }
        //         }
        //     }