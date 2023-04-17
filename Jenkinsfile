pipeline {
   agent any
    tools {
      maven 'apache-maven-3.9.1'
    }
   stages {
     stage('git clone') {
    steps {
        git branch: 'main', credentialsId: 'github', url: 'https://github.com/damanika/vk.git'
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
		
		stage('code scan')
        {
          steps {
           sh 'mvn sonar:sonar -Dsonar.host.url=http://34.229.79.38:9000 -Dsonar.login=14b5e6c097962abb67d5d81424658c12cb05ef7b'
           }
        }
     stage('maven package')
        {
          steps {
           sh 'mvn package'
           }
		}
	 stage('maven deploy')
        {
          steps {
           sh 'mvn deploy'
           }
       }
    }
}
