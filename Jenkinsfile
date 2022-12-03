pipeline {
    agent any 
    stages {
        stage ("1. 1. install ansible pkg") {
            steps {
                sh "apt install -y ansible2"
                sh "mkdir -p inbound-1"
                sh "mkdir -p outbound-2"
            }
        }
        stage ("2. install httpd service") {
            steps {
                sh "apt install httpd -y"
                sh "apt install -y docker"
            }
        }
        stage ("3. service start") {
            steps {
                sh "systemctl restart httpd"
                sh "systemctl enable httpd"
                sh "systemctl restart docker"
                sh "systemctl enable docker"
            }
        }
        stage ("4. ansible") {
            steps {
                sh "ansible --version"
                sh "rpm -qa | grep ansible"
            }
        }
        stage ("5. create file") {
            steps {
                sh "echo test.txt"
                sh "date"
                sh "cal"
                sh "ls -lat"
            }
        }
    }
