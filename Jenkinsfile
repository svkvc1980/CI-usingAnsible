pipeline {
    agent any
/*
       tools
    {
       maven "Maven"
    }
     
  */   
    stages {
      stage('checkout') {
           steps {
             
                git branch: 'master', url: 'https://github.com/svkvc1980/CI-usingAnsible.git'
             
          }
        }
         
       /*
        stage('Tools Init') {
            steps {
                script {
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
               def tfHome = tool name: 'Ansible'
                env.PATH = "${tfHome}:${env.PATH}"
                 sh 'ansible --version'
                    
            }
            }
        }
  
  */
       
         stage('Execute Maven') {
           steps {
             
                sh 'mvn package'             
          }
        }
        
        
         
        
        
        
        stage('Ansible Deploy') {
             
            steps {
                 
             
               
              // sh "ansible-playbook main.yml -i inventories/dev/hosts --user ec2-user --key-file /home/ec2-user/devopsproject.pem"

              // sh "ansible-playbook main.yml -i inventories/dev/hosts"
            sh "ansible-playbook main.yml -i inventories/dev/hosts --user ec2-user --key-file /home/ec2-user/.ssh/id_rsa"
            }
        }
    }
}
