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
           sh 'mvn sonar:sonar -Dsonar.host.url=http://44.202.166.248:9000 -Dsonar.login=76e04a2a1096e6b650ac0e8a7b7507717ce2b022'
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
