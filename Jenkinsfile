node {
     stage('Clone repository') {
         checkout scm
     }
     stage('Build image') {
         app = docker.build("jhadmin/harbor-reg")
         
     }
     stage('Push image') {
         docker.withRegistry('http://ec2-3-34-179-218.ap-northeast-2.compute.amazonaws.com/', 'harbor-reg') {
             app.push("${env.BUILD_NUMBER}")
             app.push("latest")
         }
     }
}
