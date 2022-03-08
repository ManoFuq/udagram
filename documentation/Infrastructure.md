Back-end API Environment:
    AWS Elastic Beanstalk Node.js 14 running on 64bit Amazon Linux Server
        URL - http://Newapp-env.eba-pjrm2mgm.us-east-1.elasticbeanstalk.com 
        Environment includes Postgres database - endpoint: http://database-1.cjntl6tetq1z.us-east-1.rds.amazonaws.com
        App name: newapp

Front-End:
    AWS S3 bucket: febronia
        Configured for static website hosting: http://febronia.s3-website-us-east-1.amazonaws.com

Deployment Pipeline:
    CircleCI connected to main branch of GitHub project - https://github.com/ManoFuq/udagram