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
                    echo "deployed"
            }
        }
}
}
