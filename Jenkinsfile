pipeline {
 agent {label 'master'} 

stages {
  stage('git') {
                steps {
                              git 'https://github.com/nrgO5/java_demo.git' 
                          }
                  }
  stage('maven') {
                    steps {
                        sh 'mvn clean package'
                            }
         
        }
        stage('deploy'){
        steps{
        deploy adapters: [tomcat9(credentialsId: 'b8c5ac22-2257-43f7-b913-f3119b4e19ab', path: '', url: 'http://3.19.244.195:8080/')], contextPath: 'new-app', war: '**/*war'
        }
        }
}


}
 
