# AWS News

A sample project leveraging AWS Amplify, AWS AppSync, AWS Lambda, Amazon DynamoDB, etc. This project (and a previous incarnation of it) was born out of a desire to test drive a number of new services released by AWS over the past months / year. These primarily include [Amplify DataStore](https://aws-amplify.github.io/docs/js/datastore), [Lambda Layers](https://docs.aws.amazon.com/lambda/latest/dg/configuration-layers.html), [Lambda support for Ruby](https://docs.aws.amazon.com/lambda/latest/dg//lambda-ruby.html), [AWS Step Functions Nested Workflows](https://aws.amazon.com/about-aws/whats-new/2019/08/aws-step-function-adds-support-for-nested-workflows/), and a few others. The project was also an opportunity to build and test a few ideas in a more realistic application.

The resulting product is a news reader that aggregates the various AWS blogs, creating awareness of the content, and a single location to read it. In the future, the application will also attempt to recommend content across blogs.

Project is currently hosted at: https://news.iamjkahn.com.

## Getting Started

To get started with AWS News:

### Prerequisites

AWS News requires the following prerequisites:

* [AWS Account](https://aws.amazon.com/account/)
* [Node 10+](https://nodejs.org/en/download/)
* [Amplify CLI v4.10+](https://aws-amplify.github.io/docs/cli-toolchain/quickstart#quickstart)
* [AWS SAM CLI](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-sam-cli-install.html)
* [Docker](https://docs.docker.com/install/)

> Note: AWS offers a [Free Tier](https://aws.amazon.com/free/) for many services, though not all used in this project are part of the Free Tier.

## Deployment

1. [Create a personal access token for GitHub](https://help.github.com/en/github/authenticating-to-github/creating-a-personal-access-token-for-the-command-line) with scopes `repo` and `admin:repo_hook`. Name the token "aws-news-build".
2. Copy the token value (it will not be visible again).
3. Create a new secret in AWS Secrets Manager:

  ``` bash
  aws secretsmanager create-secret --name GitHubOAuthToken --secret-string ACCESS_TOKEN
  ```

4. Deploy the build stack. In addition, we will modify the CodeBuild project created as part of this stack to use privileged mode -- this allows CodeBuild to use the Docker daemon.

  ``` bash
  make deploy.build
  ```

To deploy AWS News:

1. H

## Cleaning Up

make delete
amplify delete


## Stack


## To Do

* Add most read / latest reads
* Add personalization and auth needed
* Add analytics
* QLDB??
* Notifications?
* iOS (SwiftUI)

## Authors

* **Josh Kahn** - *Initial work*

## Acknowledgements

Heitor Lessa's [AWS Serverless Airline Booking](https://github.com/aws-samples/aws-serverless-airline-booking) project helped identify several useful patterns for managing deployment.