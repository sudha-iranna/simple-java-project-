pipeline {
agent none
parameters {
  choice choices: ['build', 'deploy', 'test'], name: 'STAGE'
}
stages {
  stage('BUILD') {
    agent {label'slave1'}
    steps {
    script {
    if (params.STAGE=='build')
    {
    git branch: 'master', url: 'https://github.com/sudha-iranna/simple-java-project-.git'
          sh 'mvn clean install'
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
      sh 'sudo cp -r /home/ec2-user/workspace/b4-assign-check/target/works-with-heroku-1.0.war /home/ec2-user/apache-tomcat-9.0.65/webapps'
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
