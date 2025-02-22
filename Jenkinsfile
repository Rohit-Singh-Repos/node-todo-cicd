@Library("shared-lib") _
pipeline {
     agent { label "jenkins-new-node-label" }
     stages{
         stage("Clone Code"){
             steps{
                 script{
                     clone("https://github.com/Rohit-Singh-Repos/node-todo-cicd","master")
                 }
             }
         }
         stage("Build and Test"){
             steps{
                 script{
                     build("node-app-test-new","latest","rohitsingh3010")
                 }
             }
         }
         stage("Push to Docker Hub"){
             steps{
                 script{
                     push("node-app-test-new","latest","rohitsingh3010")
                 }
             }
         }
         stage("Deploy"){
             steps{
                 script{
                     deploy()
                 }
             }
         }
     }
 }
