pipeline {
  agent any
  stages {
    stage('spin up instance') {
      steps {
        sh '/usr/local/bin/aws ec2 start-instances --region us-west-2 --instance-ids i-00cdc276bf60ae34f'
      }
    }

    stage('build') {
      agent {
        node {
          label 'jenkins-slave'
        }

      }
      steps {
        sh '''hostname
pwd
ls -lFa'''
      }
    }

  }
}