pipeline {
   agent any
    tools {
      maven 'apache-maven-3.9.1'
    }
   stages {
     stage('git clone') {
    steps {
       git credentialsId: 'github', url: 'https://github.com/kartikeyapro/ks.git'
     }
  }
   stage('maven clean')
    {
    steps {
     sh 'mvn clean'
    }
  }
       stage('maven test')
        {
          steps {
           sh 'mvn test'
           }
        }
      stage('maven compile')
        {
          steps {
           sh 'mvn compile'
           }
        }
     stage('maven package')
        {
          steps {
           sh 'mvn package'
           }
	 stage('maven deploy')
        {
          steps {
           sh 'mvn deploy'
           }
       }
    }
}
