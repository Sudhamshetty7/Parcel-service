pipeline {
    agent { label 'node1' }
    stages {
        stage('checkout') {
            steps {
                sh 'rm -rf Parcel-service'
                sh 'git clone https://github.com/Sudhamshetty7/Parcel-service'
            }
        }
        stage('build') {
            steps {
                sh 'mvn --version'
                sh 'mvn clean install'
                sh 'java -jar /home/slave-1/workspace/Parcel-service_feature-2/target/simple-parcel-service-app-1.0-SNAPSHOT.jar &'
            }
        } 
        stage('deploy') {
             steps {
                 sh 'scp /home/slave-1/workspace/Parcel-service_feature-2/target/simple-parcel-service-app-1.0-SNAPSHOT.jar root@172.31.5.133:/opt/apache-tomcat-8.5.98/webapps/'
}
        }
}  
}
