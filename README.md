# packer
packer


# install packer 
EXTRACT IT and COPY exe file IN C:\Program Files\packer
Add path to environment variable
clone repo and copy exe file in this repo folder

```
**IAM POLICY**

AmazonEC2FullAccess

**testing_ami**
{
	"Version": "2012-10-17",
	"Statement": [
		{
			"Effect": "Allow",
			"Action": [
				"ec2:RunInstances",
				"ec2:CreateSecurityGroup",
				"ec2:CreateKeyPair",
				"ec2:TerminateInstances",
				"ec2:DescribeInstances",
				"ec2:DescribeImages",
				"ec2:CreateTags"
			],
			"Resource": [
				"arn:aws:ec2:us-east-1:842675994865:instance/*",
				"arn:aws:ec2:us-east-1:842675994865:security-group/*",
				"arn:aws:ec2:us-east-1:842675994865:key-pair/*",
				"arn:aws:ec2:us-east-1:842675994865:image/*"
			]
		},
		{
			"Effect": "Allow",
			"Action": "iam:PassRole",
			"Resource": "arn:aws:iam::842675994865:role/EC2InstanceRole",
			"Condition": {
				"StringEquals": {
					"iam:PassedToService": "ec2.amazonaws.com"
				}
			}
		}
	]
}


```

```
**OPEN REPO FOLDER IN CMD**

packer.exe validate --var-file packer-vars.json packer.json

packer.exe inspect --var-file packer-vars.json packer.json

packer.exe build --var-file packer-vars.json packer.json
```
