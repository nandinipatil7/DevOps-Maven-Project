pipeline { 
    agent any 

    tools { 
        maven 'Maven'   
        jdk 'JDK'       
    } 

    stages { 

        stage('Checkout') { 
            steps { 
                checkout scm 
            } 
        } 

        stage('Build') { 
            steps { 
                script { 
                    if (isUnix()) { 
                        sh 'mvn clean compile' 
                    } else { 
                        bat 'mvn clean compile' 
                    } 
                } 
            } 
        } 

        stage('Test') { 
            steps { 
                script { 
                    if (isUnix()) { 
                        sh 'mvn test' 
                    } else { 
                        bat 'mvn test' 
                    } 
                } 
            } 
        } 
    } 
}
      
