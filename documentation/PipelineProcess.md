Pipeline process: Circle CI/CD connected to github repo: https://github.com/ManoFuq/udagram

Process:
	Run Front-end install and Back-end install scripts to install   dependencies.
		Front-End script: `cd udagram && cd udagram-frontend && npm install`
		Back-End script: `cd udagram && cd udagram-api && npm install`

	Run Front-end and Back-end build scripts to build app.
		Front-End script: `cd udagram && cd udagram-frontend && npm run build`
		Back-End script: `cd udagram && cd udagram-api && npm run build`

	Run Front-end and Back-end deployment scripts to deploy Back-end to AWS Elastic Beanstalk and Front-end to AWS S3 bucket.

		Front-End Script: `cd udagram && cd udagram-frontend && chmod +x ./bin/deploy.sh && ./bin/deploy.sh`

		Front-End deploy.sh contents: `aws s3 cp --recursive --acl public-read ./www s3://s3xudacity/`

		Back-End Script: `cd udagram && cd udagram-api &&chmod +x ./bin/deploy.sh && ./bin/deploy.sh`

		    Back-End deploy.sh contents: `cd ./www eb init --region us-east-1 --platform node.js newapp eb use Newapp-env eb setenv JWT_SECRET=$JWT_SECRET POSTGRES_DB=$POSTGRES_DB POSTGRES_HOST=$POSTGRES_HOST POSTGRES_PASSWORD=$POSTGRES_PASSWORD POSTGRES_PORT=$POSTGRES_PORT POSTGRES_USERNAME=$POSTGRES_USERNAME AWS_REGION=$AWS_REGION AWS_BUCKET=$AWS_BUCKET URL=$URL eb deploy`