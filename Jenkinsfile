pipeline {
    agent any
    tools{
        maven 'Maven'
    }
    stages {
        // stage("clone code"){
        //     steps{
        //        git credentialsId: 'git_credentials', url: 'https://github.com/Iliyas-shah/pipeline_tomcat_jenkins.git'
        //     }
        // }
        stage("build code"){
            steps{
              sh "mvn clean package"
            }
        }
        stage('Code Deployment'){
		steps{
		deploy adapters: [tomcat10(credentialsId: 'TomcatCreds', path: '', url: 'http://localhost:9090/')], contextPath:null, war: 'target/*.war'
		}
	    }
        // stage("deploy"){
        //     steps{
        //       sshagent(['deploy_user']) {
        //          sh "scp -o StrictHostKeyChecking=no webapp/target/webapp.war ec2-user@13.229.183.126:/opt/apache-tomcat-8.5.55/webapps"
                 
        //         }
        //     }
        // }
    }
}
