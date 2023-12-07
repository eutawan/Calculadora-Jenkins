pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                bat 'mvn clean package -DskipTests=true'
            }
        }
        stage('Test'){
            steps{
                bat 'mvn test'
            }
        }
        stage('Deploy'){
            steps{
                deploy adapters: [tomcat9(credentialsId: 'TomcatLogin2', path: '', url: 'http://localhost:4002/')], contextPath: 'calculadora', war: 'target/calculadora.war'
            }
        }
    }
}