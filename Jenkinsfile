properties([pipelineTriggers([githubPush()])])
node('linux') {
    git url: 'https://github.com/rossweinstein/infrastructure-pipeline.git', branch: 'master'
    stage('Test') {
        sh "env"
    }
    stage ("GetInstances") {

        sh "aws ec2 describe-instances --region us-east-1"


    }

    stage ("CreateInstance") {
        sh "aws ec2 run-instances --image-id ami-467ca739 --count 1 --instance-type t2.micro --key-name seis665-classroom-key --security-group-ids sg-0eabd347 --subnet-id subnet-f6f4b2c9 --region us-east-1"

    }
}