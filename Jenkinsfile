pipeline{
    agent{
        label{
            label '172.31.32.122'
            customWorkspace "/data/pipeline"
        }
    }
    stages{
        stage('install-git'){
            steps{
                sh "sudo chmod -R 777 /data/pipeline"
                sh "sudo yum install git -y"
                sh "sudo git clone https://github.com/Kushal-1412/multi-11.git -b 22Q2"
            }
        }
        stage('install-httpd'){
                steps{
                    sh "sudo yum install httpd -y"
                }
        }
        stage('copy-index'){
            steps{
                sh "sudo cp -r index.html /var/www/html/"
                sh "sudo chmod -R 777 /var/www/html/index.html"
            }
        }
        stage('restart-httpd'){
            steps{
                sh "sudo service httpd restart"
            }
        }
    }
}
