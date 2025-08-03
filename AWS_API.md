# AWS API - Short Note

The **AWS API (Amazon Web Services Application Programming Interface)** allows developers to interact with AWS services programmatically via HTTP requests. It supports managing resources, automating tasks, and integrating cloud capabilities into applications.

## Key Features

- **RESTful Interface**: Most AWS APIs are REST-based, using standard HTTP methods like `GET`, `POST`, `PUT`, and `DELETE`.
- **Service Endpoints**: Each AWS service exposes its API through specific **regional endpoints** (e.g., `https://ec2.us-east-1.amazonaws.com`). These endpoints are required when making direct API calls.
- **Signed Requests**: All AWS API calls must be **signed using AWS Signature Version 4**, which involves hashing and encrypting parts of the request using your access key and secret key for authentication and security.
- **SDK Support**: AWS provides SDKs for many languages (Python, JavaScript, Java, etc.) that abstract away much of the signing and request logic.

## Using Postman with AWS APIs

You can use **Postman** to test AWS APIs, but you must manually sign the request or use environment variables and pre-request scripts to automate signing. Postman does **not natively sign AWS requests**, so tools or scripts (like AWS Signature v4 Postman Pre-request Script) are needed.

### Example with Postman

1. Set method: `POST`
2. Set URL: `https://iam.amazonaws.com/`
3. Add required headers (including signed `Authorization` header)
4. Use AWS Signature V4 script or external tool to generate signed headers

## Common Use Cases

- Automating EC2 instance creation
- Uploading files to S3
- Triggering AWS Lambda functions
- Managing IAM roles and policies

## Example CLI Call (uses signed request internally)

```bash
aws s3api list-buckets
