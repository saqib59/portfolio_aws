
# Host a static website on AWS S3 with AWS CodePipeline.

A brief description on how to connect your static website hosted on Aws s3 with the help of Aws CodePipeline.


## Lab Overview



To push your code from GitHub to an Amazon S3 bucket, you can use the AWS CodePipeline service. Here's an outline of the steps you can follow:

- Set up an AWS account and create an IAM user with permissions to access S3 and CodePipeline.
- Create an S3 bucket to store your code.
- Enable static website hosting for the bucket. To enable static website hosting, you will need to set the bucket's static website hosting configuration and specify the name of the index document and the error document.
- Connect your GitHub repository to CodePipeline by following the instructions in the AWS documentation.
- Create a new CodePipeline pipeline, and choose GitHub as the source provider.
- In the pipeline configuration, specify the name of the S3 bucket you created as the destination for your code.
- Configure the build and deployment stages of your pipeline as needed. You may need to create an Amazon Elastic Container Registry (ECR) repository and an Amazon Elastic Container Service (ECS) cluster to deploy your code to.
- Run the pipeline to deploy your code from GitHub to S3.

## Route 53

- To redirect it to a specific domain you can add an record for your s3 bucked in your route 53 dashboard.

- You must give the bucket the same name as the record that you want to use to route traffic to the bucket. For example, if you want to route traffic for example.com to an S3 bucket that is configured for website hosting, the name of the bucket must be example.com.

Alternatively, you can also use the AWS CLI to sync the contents
of your GitHub repository to an S3 bucket. To do this, you
can use the aws s3 sync command and specify the path to your 
local repository as the source and the name of your S3 bucket
as the destination.



For example:

```bash
  aws s3 sync path/to/local/repository s3://my-bucket

```

This will upload all the files in your repository to the S3 bucket.






