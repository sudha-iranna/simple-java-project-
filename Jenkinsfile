pipeline {
agent none
parameters {
  choice choices: ['build', 'deploy', 'test'], name: 'STAGE'
}
stages {
  stage('BUILD') {
  agent any
    steps {
    script {
    if (params.STAGE=='build')
    {
    git branch: 'main', url: 'https://github.com/sudha-iranna/j-project.git'
     sh 'echo "this is build stage"'
               }
         else {
         echo "skipping build stage"
         }
         
         }
     }
  }

  stage('DEPLOY') {
  agent any
    steps {
     script {
    if (params.STAGE=='deploy')
    {
      echo "this is deploy stage"
      sh 'sleep 5'
    }
    else {
    echo "skipping deploy stage"
    }
    }
      }  
   }

  stage('TEST') {
  agent {label'slave2'}
    steps {
    script {
    if (params.STAGE=='test') {
     sh 'echo "this is testing stage"'
    }
    else {
    echo "skipping test stage"
    }
    }
    }
  }

}


}
