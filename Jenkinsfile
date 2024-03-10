pipeline{
    agent any 
        stages{
              stage('clone repository'){
                steps{
                    checkout([$class:'GitSCM',
                    branches:[[name:'*/main']],
                    userRemoteConfigs: [[url:'https://github.com/Niki1320/PES2UG21CS338_Nikitha_V.git']]])
                }
              }
              stage('Build'){
                steps{
                    build 'PES2UG21CS338-1'
                    sh 'g++ Jenkins.cpp -o output'
                    echo 'Build Stage Successful'
                }
              }
              stage('Test'){
                steps{
                    sh './output'
                    echo 'test stage successfully'
                }
              }
              stage('Deploy'){
                steps{
                    echo 'deployment successfull'
                }
              }
        }
        post{
            failure{
                echo 'pipeline failed'
            }
        }
    }
