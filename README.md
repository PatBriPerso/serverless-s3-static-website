serverless-s3-static-website
---

This repository contains a template to use with [serverless framework](https://www.serverless.com/). 
It deploy a static website on [AWS S3](https://aws.amazon.com/s3/) bucket.

# Usage

## prerequisites
You need to have an AWS account. Create one here: https://aws.amazon.com/free/. And you need to setup 
your computer with your access key and your secret key.

You need to install serverless framework. You can 
[follow their documentation](https://www.serverless.com/framework/docs/getting-started).

I'm a linux user and I choose to install serverless framework as a standalone binary:

```bash
curl -o- -L https://slss.io/install | bash
```


## Use this template

You can create your own static website project `my-website` based on this template with this command:

```bash
serverless create --template-url=https://github.com/PatBriPerso/serverless-s3-static-website --path=my-website
```

Then you can initialise the project and deploy the website with these commands:

```bash
cd my-website
serverless plugin install -n serverless-s3-sync
serverless deploy --verbose
```

At the end of the deploy step, you will see:
```
Stack Outputs:
  WebsiteBucketName: my-website-dev-serverless
  WebsiteBucketUrl: http://my-website-dev-serverless.s3-website.eu-west-3.amazonaws.com
  ServerlessDeploymentBucketName: my-website-dev-serverlessdeploymentbucket-g9lcz624p7nm
```

The `WebsiteBucketUrl` is your static website URL. Open it in your browser to see the content.

## Change your website content

serverless deploy the files that are in the `./static` directory. Just change, add or remove the files,
issue the command `serverless deploy` and your website will be updated.
