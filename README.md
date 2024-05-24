# Overview
This project implements a photo album web application that can be searched using natural language text. Utilizing AWS services such as Lex, ElasticSearch, and Rekognition, this application allows users to upload, index, and search for photos based on detected labels and custom metadata.

## Architecture Diagram

![image](https://github.com/rohnnie/PicFinder/assets/46161834/65de225a-fee4-40ae-b6aa-2a9c188e2fb6)

### Features
1. Photo Upload & Indexing: Users can upload photos, which are automatically labeled using Amazon Rekognition and indexed in ElasticSearch.
2. Natural Language Search: Users can search for photos using natural language queries, handled by an Amazon Lex bot.
3. Custom Labels: Users can add custom labels to photos during upload, enhancing search capabilities.
4. Frontend Interface: A simple web interface allows for uploading photos, entering custom labels, and searching the photo album.

### Setup and Deployment

#### Prerequisites
1. AWS Account
2. Node.js and NPM
3. AWS CLI configured with appropriate permissions

#### Steps
**1. Launch ElasticSearch Instance**

Create an ElasticSearch domain named photos using the AWS ElasticSearch service.

**2. Upload & Index Photos**

- **Create S3 Bucket**: Create an S3 bucket (B2) to store photos.
- **Create Lambda Function (LF1)**: Implement the `index-photos` Lambda function.
- **Set Up S3 Event Trigger**: Configure a PUT event trigger on the S3 bucket to invoke `index-photos` Lambda function.

**3. Search**

- **Create Lambda Function (LF2)**: Implement the search-photos Lambda function.
- **Create Lex Bot**: Create an Amazon Lex bot with an intent named SearchIntent for handling search queries.

**4. Build the API Layer**

- **Create API Gateway**: Define API methods for PUT /photos and GET /search.
- **Deploy the API**: Generate and integrate the SDK into the frontend.

**5. Frontend**

- **Create S3 Bucket for Frontend**: Set up static website hosting.
- **Build Frontend Application**: Implement photo upload and search functionality.

**6. Deploy Using CodePipeline**

**Define Pipelines**: Set up pipelines for Lambda functions and frontend code.

**7. CloudFormation Template**

Create a CloudFormation template (T1) to provision necessary AWS resources.

## Conclusion

With this setup, you will have a fully functional photo album application capable of natural language search and automated photo indexing using AWS services.


