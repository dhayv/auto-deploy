# S3 Static Website CI/CD Pipeline

Automate static website deployments using AWS CodePipeline and S3, replacing traditional FTP uploads with a modern CI/CD approach. This repository demonstrates automated deployments with version control, rollback capabilities, and zero-touch updates.

[View Full Tutorial](https://dev.to/dhayv/automating-website-deployments-with-aws-codepipeline-and-s3-no-upload-el8)

## Architecture
![Lucid Architecture](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/hhc8ojuzon5atmo5zuxb.png)

## Tech Stack
- GitHub (Source Control)
- AWS CodePipeline (Deployment Automation)
- Amazon S3 (Static Website Hosting)
- AWS IAM (Security Management)

## Features
✨ Zero-touch deployments  
🔄 Automatic updates on push  
📦 S3 versioning enabled  
🔧 Easy rollback capability  
🛡️ IAM security controls  

## Quick Start
1. Fork this repository
2. Create an S3 bucket with static website hosting
3. Set up AWS CodePipeline with GitHub integration
4. Push changes to automatically deploy

## Repository Structure
```
├── index.html          # Sample static website
└── README.md          # Documentation
```

## Setup Requirements
- AWS Account with administrative access
- GitHub account
- Basic understanding of AWS services
- Static website files

## Configuration Files

### Sample index.html
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Codepipeline Demo</title>
</head>
<body>
    <H1>Deploy via AWS Codepipeline</H1>
    <p>Deployment version: <span>1</span></p>
</body>
</html>
```

### Required AWS Configuration
1. S3 Bucket Policy
```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": [
                "s3:GetObject"
            ],
            "Resource": "arn:aws:s3:::your-bucket-name/*"
        }
    ]
}
```

## Implementation Steps
1. GitHub Repository Setup
   - Create repository
   - Add initial website files
   
2. S3 Configuration
   - Create bucket with unique name
   - Enable static website hosting
   - Configure public access
   - Enable versioning
   - Set bucket policy

3. CodePipeline Setup
   - Create new pipeline
   - Connect GitHub source
   - Configure S3 deployment
   - Enable automatic triggers

## Troubleshooting
- **Pipeline Failures:** Check source configuration and IAM permissions
- **S3 Access Issues:** Verify bucket policy and public access settings
- **Website Not Loading:** Confirm static website hosting is enabled
- **Updates Not Deploying:** Check GitHub webhook configuration

## Contributing
1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Open a Pull Request

## License
This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.

## Resources
- [Tutorial Blog Post](https://dev.to/dhayv/automating-website-deployments-with-aws-codepipeline-and-s3-no-upload-el8)
- [AWS S3 Documentation](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html)
- [AWS CodePipeline Documentation](https://docs.aws.amazon.com/codepipeline/latest/userguide/welcome.html)
