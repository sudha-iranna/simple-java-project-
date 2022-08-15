pipeline{
      agent none 
      stages{
          stage ('BUILD')
                 {
                 agent {
                      label 'label-C'
                          }
               steps {
                git branch: 'master', url: 'https://github.com/SushrutaEswar/simple-java-project.git'
               sh 'mvn clean install'
                           }
                           }
            stage ('DEPLOY')
            {
                  agent {
                  label 'label-J'
                  }
                  steps {
                        sudo cp -r /home/ec2-user/workspace/pipeline2/target/works-with-heroku-1.0.war /opt/apache-tomcat-9.0.65/webapps
                        }
                    }
}
}
