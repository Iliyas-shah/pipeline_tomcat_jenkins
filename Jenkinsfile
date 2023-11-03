// cd C:\Users\iliyas\my-app
// java -cp target/my-app-1.0-SNAPSHOT.jar com.mycompany.app.App
// pipeline {
//     agent any
//     tools{
//         maven 'Maven'
//     }
//     stages {
//         // stage("clone code"){
//         //     steps{
//         //        git credentialsId: 'git_credentials', url: 'https://github.com/Iliyas-shah/pipeline_tomcat_jenkins.git'
//         //     }
//         // }
//         stage("build code"){
//             steps{
//               sh "mvn clean install"
//             }
//         }
//         stage('Code Deployment'){
// 		steps{
// 		deploy adapters: [tomcat10(credentialsId: 'TomcatCreds', path: '', url: 'http://localhost:9090/')], contextPath:null, war: 'target/*.war'
// 		}
// 	    }
//         // stage("deploy"){
//         //     steps{
//         //       sshagent(['deploy_user']) {
//         //          sh "scp -o StrictHostKeyChecking=no webapp/target/webapp.war ec2-user@13.229.183.126:/opt/apache-tomcat-8.5.55/webapps"
                 
//         //         }
//         //     }
//         // }
//     }
// }
// pipeline {
//     agent any
//     environment {
//         PATH = "/opt/apache-maven-3.6.3/bin:$PATH"
//     }
//     stages {
//         stage("clone code"){
//             steps{
//                git credentialsId: 'git_credentials', url: 'https://github.com/ravdy/hello-world.git'
//             }
//         }
//         stage("build code"){
//             steps{
//               sh "mvn clean install"
//             }
//         }
//         stage("deploy"){
//             steps{
//               sshagent(['deploy_user']) {
//                  sh "scp -o StrictHostKeyChecking=no webapp/target/webapp.war ec2-user@13.229.183.126:/opt/apache-tomcat-8.5.55/webapps"
                 
//                 }
//             }
//         }
//     }
// }
// <user username="tomcat" password="password" roles="manager-gui, admin-gui, manager-script"/>
pipeline{
    agent any
    tools{
        maven 'Maven'
    }
    stages{
        stage("Git Clone"){
            steps{
                git 'https://github.com/Iliyas-shah/pipeline_tomcat_jenkins.git'
            }
        }
        stage("Build"){
            steps{
                bat'mvn clean install'
            }
        }
        stage("Deploy"){
            steps{
                deploy adapters: [tomcat9(credentialsId: 'TomcatCreds', path: '', url: 'http://localhost:9090/')], contextPath:null, war: '**/*.war'
            }
        }
    }
}
