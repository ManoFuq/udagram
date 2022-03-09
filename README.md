# Udagram App
# Preparing source code infrastructure for deployment

## Write the environment variables

- Environment variables of AWS elastic beanstalk configuration of environment Newapp-env

  - AWS_BUCKET=febronia
  - AWS_PROFILE=default
  - AWS_REGION=us-east-1
  - JWT_SECRET=admin
  - URL = http://localhost

### Image for the environment health
![health](https://i.ibb.co/MNSdtSn/Screenshot-326.png)

- Environment variables CircleCI

  - AWS_ACCESS_KEY_ID=AKIAS2Z7YB3BKENHJZEX
  - AWS_SECRET_ACCESS_KEY=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

### Image for S3 
![S3](https://i.ibb.co/f1DQCjb/Screenshot-293.png)

## The project scripts
```
    "scripts": {
        "install:frontend": "cd udagram && cd udagram-frontend && npm install",
        "install:backend": "cd udagram && cd udagram-api && npm install",
        "build:frontend": "cd udagram && cd udagram-frontend && npm run build",
        "build:backend": "cd udagram && cd udagram-api && npm run build",
        "test:frontend":"cd udagram && cd udagram-frontend && npm run test",
        "test:backend":"cd udagram && cd udagram-api && npm run test",
        "deploy:frontend": "cd udagram && cd udagram-frontend && npm run deploy",
        "deploy:backend": "cd udagram && cd udagram-api && npm run deploy"
    }
```
### Image for frontend page
![frontend page](https://i.ibb.co/Db414xH/Screenshot-343.png)
## Configure the AWS RDS database

- POSTGRES_USERNAME=postgres
- POSTGRES_PASSWORD=z4h4k39a0sL1TqLNCegb
- POSTGRES_DB=postgres
- DB_PORT=5432
- POSTGRES_HOST=database-1.cjntl6tetq1z.us-east-1.rds.amazonaws.com

### Image for the database 
![database](https://i.ibb.co/hCQC7rP/Screenshot-259.png)



### GitHub repo link
- https://github.com/ManoFuq/udagram 

### image for CircleCI environment variables
![variables](https://i.ibb.co/YbdS1R9/Screenshot-346.png)

## Write a proper pipeline file using the config.yml format used by CircleCi

- .circleci/config.yml

## Write code that demonstrates a well-organized docs folder
- Dep.md
- Infrastructure.md
- Pipeline.md
# Diagrams
## Image of a Pipeline diagram
![pipeline](https://i.ibb.co/6YVQxGt/pipline-drawio.png)

## Image of Infrastructure diagram
![Infrastructure](https://i.ibb.co/2hfnYxy/Infrastructure-diagram-drawio.png)

# Udagram

This application is provided to you as an alternative starter project if you do not wish to host your own code done in the previous courses of this nanodegree. The udagram application is a fairly simple application that includes all the major components of a Full-Stack web application.

## Getting Started

1. Clone this repo locally into the location of your choice.
1. Move the content of the udagram folder at the root of the repository as this will become the main content of the project.
1. Open a terminal and navigate to the root of the repository 
1. follow the instructions in the installation step

The project can run but is missing some information to connect to the database and storage service. These will be setup during the course of the project


### Back-End scripts
```
        "start": "node .",
        "tsc": "npx tsc",
        "dev": "ts-node-dev --respawn --transpileOnly ./src/server.ts",
        "deploy": "chmod +x bin/deploy.sh && bin/deploy.sh",
        "prod": "npx tsc && node ./www/server.js",
        "clean": "rm -rf www/ || true",
        "copy:scripts": "@powershell copy src/config www/config && @powershell copy ./.npmrc ./www/.npmrc && @powershell copy ./package.json ./www/package.json  ",
        "build": "npm run clean && tsc && cp -rf src/config www/config && cp .npmrc www/.npmrc && cp package.json www/package.json && cd www && zip -r Archive.zip . && cd ..",
        "test": "echo \"Error: no test specified\" && exit 1"
```

### Back-End Dependencies

```
        "@types/bcrypt": "^3.0.0",
        "@types/jsonwebtoken": "^8.3.2",
        "aws-sdk": "^2.429.0",
        "bcrypt": "^5.0.1",
        "body-parser": "^1.18.3",
        "cors": "^2.8.5",
        "dotenv": "^8.2.0",
        "email-validator": "^2.0.4",
        "express": "^4.16.4",
        "jsonwebtoken": "^8.5.1",
        "node": "^14.15.1",
        "pg": "^8.7.1",
        "reflect-metadata": "^0.1.13",
        "sequelize": "^5.21.4",
        "sequelize-typescript": "^0.6.9"

```
### Back-End devDependencies
```
        "@types/bluebird": "^3.5.26",
        "@types/cors": "^2.8.6",
        "@types/express": "^4.16.1",
        "@types/node": "^11.11.6",
        "@types/sequelize": "^4.27.44",
        "@types/validator": "^10.9.0",
        "@typescript-eslint/eslint-plugin": "^2.19.2",
        "@typescript-eslint/parser": "^2.19.2",
        "chai": "^4.2.0",
        "chai-http": "^4.2.1",
        "eslint": "^6.8.0",
        "eslint-config-google": "^0.14.0",
        "mocha": "^6.1.4",
        "ts-node-dev": "^1.0.0-pre.32",
        "typescript": "^3.3.4000"
```
### Front-End scripts
```
        "ng": "ng",
        "start": "ng serve",
        "build": "ng build",
        "test": "ng test",
        "lint": "ng lint",
        "e2e": "ng e2e",
        "deploy": "chmod +x bin/deploy.sh && bin/deploy.sh"
```

### Front-End Dependencies
```
        "@angular/common": "^8.2.14",
        "@angular/core": "^8.2.14",
        "@angular/forms": "^8.2.14",
        "@angular/http": "^7.2.2",
        "@angular/platform-browser": "^8.2.14",
        "@angular/platform-browser-dynamic": "^8.2.14",
        "@angular/router": "^8.2.14",
        "@ionic-native/core": "^5.0.0",
        "@ionic-native/splash-screen": "^5.0.0",
        "@ionic-native/status-bar": "^5.0.0",
        "@ionic/angular": "^4.1.0",
        "core-js": "^2.5.4",
        "node": "^14.15.1",
        "rxjs": "~6.5.4",
        "zone.js": "~0.9.1"
```

### Front-End DevDependencies
```
        "@angular-devkit/architect": "~0.12.3",
        "@angular-devkit/build-angular": "^0.803.24",
        "@angular-devkit/core": "~7.2.3",
        "@angular-devkit/schematics": "~7.2.3",
        "@angular/cli": "~8.3.25",
        "@angular/compiler": "~8.2.14",
        "@angular/compiler-cli": "~8.2.14",
        "@angular/language-service": "~8.2.14",
        "@ionic/angular-toolkit": "~1.4.0",
        "@types/jasmine": "~2.8.8",
        "@types/jasminewd2": "~2.0.3",
        "@types/node": "~10.12.0",
        "@typescript-eslint/eslint-plugin": "^2.20.0",
        "@typescript-eslint/parser": "^2.20.0",
        "codelyzer": "~4.5.0",
        "jasmine-core": "~2.99.1",
        "jasmine-spec-reporter": "~4.2.1",
        "karma": "~3.1.4",
        "karma-chrome-launcher": "~2.2.0",
        "karma-coverage-istanbul-reporter": "~2.0.1",
        "karma-jasmine": "~1.1.2",
        "karma-jasmine-html-reporter": "^0.2.2",
        "protractor": "~5.4.0",
        "ts-node": "~8.0.0",
        "tslint": "~5.12.0",
        "typescript": "^3.4.5"
```


### Unit Tests:

Unit tests are using the Jasmine Framework.

### End to End Tests:

The e2e tests are using Protractor and Jasmine.

## Built With

- [Angular](https://angular.io/) - Single Page Application Framework
- [Node](https://nodejs.org) - Javascript Runtime
- [Express](https://expressjs.com/) - Javascript API Framework

## License

[License](LICENSE.txt)
 
