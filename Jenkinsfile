pipeline {
    agent any 
    stages {
        stage('Clean') {
            steps {
                println "==Clean=="
                sh 'pwd > console.txt'
                sh 'ls -al >> console.txt'
                sh 'sudo /usr/local/apache-maven-3.6.3/bin/mvn --version  >> console.txt'
                sh 'sudo /usr/local/apache-maven-3.6.3/bin/mvn clean >> console.txt'
            }
        }
        stage('Compile') { 
            steps {
                println "==Compile==" 
                sh 'sudo /usr/local/apache-maven-3.6.3/bin/mvn compile >> console.txt'
            }
        }
        stage('Test') { 
            steps {
                println "==Test=="
                sh 'sudo /usr/local/apache-maven-3.6.3/bin/mvn test >> console.txt'
            }
        }
        stage('Package') { 
            steps {
                println "==Package=="
                sh 'sudo /usr/local/apache-maven-3.6.3/bin/mvn package >> console.txt'
            }
        }
        stage('Install') { 
            steps {
                println "==Install=="
                sh 'sudo /usr/local/apache-maven-3.6.3/bin/mvn install >> console.txt'
            }
        }
        stage('Deploy') { 
            steps {
                println "==Deploy=="
                sh 'sudo /usr/local/apache-maven-3.6.3/bin/mvn tomcat7:deploy >> console.txt'
            }
        }
    }
    post{
        success{
            sh 'echo "======== 项目pipeline_javaweb_1流水线式构建部署完毕 ========"'
        }
    }
}

