##IAM Policies

{
  "Version": "2012-10-17",
  "Statement": [
 {
            "Effect": "Allow",
            "Action": "logs:CreateLogGroup",
            "Resource": "arn:aws:logs:us-west-2:976860464748:*"
    },
    {
            "Effect": "Allow",
            "Action": [
                "logs:CreateLogStream",
                "logs:PutLogEvents"
            ],
            "Resource": [
                "arn:aws:logs:us-west-2:976860464748:log-group:/aws/lambda/AutoTag:*"
            ]
    },
    {
      "Sid": "autoTagPolicy",
      "Action": [
        "ec2:CreateTags",
        "ec2:DescribeInstances",
      ],
      "Effect": "Allow",
      "Resource": "arn:aws:ec2:::*"
    }
  ]
}


##Trust Relationship

{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "Service": "lambda.amazonaws.com"
      },
      "Action": "sts:AssumeRole"
    }
  ]
}
