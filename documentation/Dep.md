AWS infrastructure requirements:
	AWS IAM user configured with permissions for deploying newapp application
	An AWS S3 bucket configured for Static Website Hosting to host the front-end webpage
	AWS Elastic Beanstalk Environment running at Node.js 14
	AWS RDS instance running a Postgres database

Build & Deployment environment requirements:
	AWS CLI to deploy front-end
	AWS Elastic Beanstalk CLI to deploy the Back-end
	NodeJS 14

For CI/CD Pipeline:
	CircleCI project  connected to a GitHub repo
	node
	aws-cli
	aws-elastic-beanstalk 