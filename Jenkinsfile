pipeline{
    agent any
    stages{
        stage('SCM-Checkout'){
            steps{
            git 'https://github.com/rshruti/maven-modular.git'
            }
        }
         stage('Build'){
            steps{
                sh '/opt/maven/bin/mvn clean package -Dmaven.test.skip=true'                
            }
        }  
        
        stage('Release'){
            steps{
                  sh '/opt/maven/bin/mvn --batch-mode release:clean release:prepare release:perform -DreleaseVersion=1.9 -DdevelopmentVersion=2.0-SNAPSHOT'               
            }
        }
        }
}
