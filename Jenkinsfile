pipeline{
      agent none 
          stage ('BUILD')
                 {
                 agent {
                      label 'label-C'
                          }
               steps {
                git branch: 'main', url: 'https://github.com/SushrutaEswar/simple-java-project.git'
               sh 'mvn clean install'
                           }
                           }
        }
             
