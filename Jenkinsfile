pipeline{
    agent{
        label{
            label '172.31.32.122'
        }
    }
    stages{
        stage('install-git'){
            steps{
                sh "sudo yum install java-1.8.0-openjdk-devel-debug.x86_64 -y"
                sh "sudo yum install git -y"
                sh "sudo rm -rf multi-11"
                sh "sudo git clone -b 22Q2 --single-branch https://github.com/Kushal-1412/multi-11.git"
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
