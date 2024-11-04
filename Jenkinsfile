pipeline {
        agent any
        tools {
            //Install Maven as M3 (we did it earlier)
            maven "M3"
        }
        stages {
            stage('Checkout') {
                steps {
                    //Code from GitHub
                    git branch: 'main', url: 'https://github.com/NevaDobric/lbg-hello-world-maven.git'
                }
            }
            stage('Compile') {
                steps {
                    //Run Maven on Unix agent
                    sh "mvn clean compile"
                }
            }
            
            stage('Test') {
                
                steps { sh 'mvn -D.maven.compile.skip test'}
                
            }
            
            stage('Package') {
                
                steps { sh 'mvn -D.maven.test.skip -D.maven.compile.skip package'}
                
            }
                
        }
}
