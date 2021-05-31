<p align="center">
  <a href="http://nestjs.com/" target="blank"><img src="https://nestjs.com/img/logo_text.svg" width="320" alt="Nest Logo" /></a>
</p>

[circleci-image]: https://img.shields.io/circleci/build/github/nestjs/nest/master?token=abc123def456
[circleci-url]: https://circleci.com/gh/nestjs/nest

  <p align="center">A progressive <a href="http://nodejs.org" target="_blank">Node.js</a> framework for building efficient and scalable server-side applications.</p>
    <p align="center">
<a href="https://www.npmjs.com/~nestjscore" target="_blank"><img src="https://img.shields.io/npm/v/@nestjs/core.svg" alt="NPM Version" /></a>
<a href="https://www.npmjs.com/~nestjscore" target="_blank"><img src="https://img.shields.io/npm/l/@nestjs/core.svg" alt="Package License" /></a>
<a href="https://www.npmjs.com/~nestjscore" target="_blank"><img src="https://img.shields.io/npm/dm/@nestjs/common.svg" alt="NPM Downloads" /></a>
<a href="https://circleci.com/gh/nestjs/nest" target="_blank"><img src="https://img.shields.io/circleci/build/github/nestjs/nest/master" alt="CircleCI" /></a>
<a href="https://coveralls.io/github/nestjs/nest?branch=master" target="_blank"><img src="https://coveralls.io/repos/github/nestjs/nest/badge.svg?branch=master#9" alt="Coverage" /></a>
<a href="https://discord.gg/G7Qnnhy" target="_blank"><img src="https://img.shields.io/badge/discord-online-brightgreen.svg" alt="Discord"/></a>
<a href="https://opencollective.com/nest#backer" target="_blank"><img src="https://opencollective.com/nest/backers/badge.svg" alt="Backers on Open Collective" /></a>
<a href="https://opencollective.com/nest#sponsor" target="_blank"><img src="https://opencollective.com/nest/sponsors/badge.svg" alt="Sponsors on Open Collective" /></a>
  <a href="https://paypal.me/kamilmysliwiec" target="_blank"><img src="https://img.shields.io/badge/Donate-PayPal-ff3f59.svg"/></a>
    <a href="https://opencollective.com/nest#sponsor"  target="_blank"><img src="https://img.shields.io/badge/Support%20us-Open%20Collective-41B883.svg" alt="Support us"></a>
  <a href="https://twitter.com/nestframework" target="_blank"><img src="https://img.shields.io/twitter/follow/nestframework.svg?style=social&label=Follow"></a>
</p>
  <!--[![Backers on Open Collective](https://opencollective.com/nest/backers/badge.svg)](https://opencollective.com/nest#backer)
  [![Sponsors on Open Collective](https://opencollective.com/nest/sponsors/badge.svg)](https://opencollective.com/nest#sponsor)-->

# Nest configuration

## Description

[Nest](https://github.com/nestjs/nest) framework TypeScript starter repository.

## Installation

```bash
$ npm install
```

## Running the app

```bash
# development
$ npm run start

# watch mode
$ npm run start:dev

# production mode
$ npm run start:prod
```

## Test

```bash
# unit tests
$ npm run test

# e2e tests
$ npm run test:e2e

# test coverage
$ npm run test:cov
```

# DynamoDB Offiline configuration

All configuration are already present within the serverless.yml configuration file. 

The serverless.yml is the oficial file to configure an application deploy in AWS. More information in: https://www.serverless.com/

## Install Serverless
```
$ npm install -g serverless

$ npm i -g serverless-offline
```

## install DynamoDB locally to run it offline
```
$ serverless dynamodb install
```
## Build and run the Serverless application
```
$ npm run build && serverless offline start
```
## Deploying application in AWS
```
$ npm run build && serverless deploy
```
Make sure, we always build our application before deploying to AWS. Because all the changes will reflect after the build process is successful as we upload the files from the directory into AWS S3 <code>.dist </code> folder.

## Some Considerations
The version of the serverless project is more current than in the article (see references), so some settings must be added in the serverless.yml file to avoid errors warnings during a run.

```bash
provider:
	  iamRoleStatements
	
# It was replaced by:

provider:
  iam:
    role:
      statements:
	
# The following variables have been added within serverless.ym to avoid warnings during the run
	
variablesResolutionMode: 20210326
configValidationMode: warn
provider:
  lambdaHashingVersion: 20201221

```
## References

<b>Use DynamoDB in NestJS Application With Serverless Framework on AWS</b><br>
https://medium.com/swlh/use-dynamodb-in-nestjs-application-with-serverless-framework-on-aws-85db02b24a34

<b>Run NestJS Application in Serverless Framework on AWS</b><br>
https://medium.com/swlh/run-nestjs-application-in-serverless-framework-on-aws-a93a75b8b6c6

<b>serverless</b><br>
https://www.serverless.com/


## Support

Nest is an MIT-licensed open source project. It can grow thanks to the sponsors and support by the amazing backers. If you'd like to join them, please [read more here](https://docs.nestjs.com/support).

## Stay in touch

- Author - [Kamil Myśliwiec](https://kamilmysliwiec.com)
- Website - [https://nestjs.com](https://nestjs.com/)
- Twitter - [@nestframework](https://twitter.com/nestframework)

## License

Nest is [MIT licensed](LICENSE).

