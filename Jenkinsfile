pipeline {
    agent any

    stages {
        stage('Lint HTML') {
            steps {
                sh 'tidy -q -e *.html'
            }
        }
        stage('Retrieve EC2 Public IP') {
            steps {
                script {
                    def awsRegion = 'ap-south-1' // Replace with your AWS region
                    def ec2InstanceId = 'i-0b9816bc51c2dc387' // Replace with your EC2 instance ID

                    // Use the AWS credentials you configured in Jenkins
                    withAWS(credentials: 'AWS', region: awsRegion) {
                        def ec2PublicIp = sh(
                            script: "aws ec2 describe-instances --region $awsRegion --instance-ids $ec2InstanceId --query 'Reservations[0].Instances[0].PublicIpAddress' --output text",
                            returnStatus: true
                        ).trim()

                        if (ec2PublicIp) {
                            echo "EC2 Public IP: $ec2PublicIp"
                        } else {
                            error "Failed to retrieve EC2 Public IP."
                        }
                    }
                }
            }
        }
        stage('Upload to AWS S3') {
            steps {
                script {
                    // Replace 'your-s3-bucket' and 'your-path' with your specific values
                    def s3Bucket = 'codedeploybuckettest123'
                    def s3Path = 'var/www/html/index.html'

                    def s3Object = [
                        entries: [
                            [
                                file: 'index.html',
                                path: s3Path
                            ]
                        ],
                        bucket: s3Bucket
                    ]

                    // Use the AWS credentials you configured in Jenkins
                    withAWS(credentials: 'your-aws-credentials-id', region: awsRegion) {
                        s3Upload(entries: [s3Object])
                    }
                }
            }
        }
    }
}
