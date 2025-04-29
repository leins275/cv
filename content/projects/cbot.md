---
draft: false
dates: Nov 2023 - Till Now (1 year 3 months)
title: LLM based chatbot
client: Merck Sharp & Dohme Corp. USA; Life Sciences & Healthcare
summary: Chatbot that helps users to find the relevant company documents according to their requests 
---

# Responsibilities
## Maintain CI/CD pipelines 
During the project I maintained Jenkins pipelines for CI/CD and other automation Jobs.  

I handled migration from Jenkins pipelines to GitHub Actions, which involves CI/CD process refactoring. Also, during this migration I connected our pipeline with artifactory to store all the artifacts for lambda functions.

## Declare new infrastructure via terraform 
I created a new test environment from scratch. According to MERCK policies, we have some security restrictions. First, public internet access was managed by a dedicated CloudFront team. To publish our new UI, I had to provide them with our S3 bucket credentials and then paste their policy into the ui bucket. Also, we have cognito authorization with custom Amazon Cognito pools, so this setting was overwritten with CloudFront team infra code. Also, I requested and set up a new VPC endpoint for the API gateway. 

## In MERCK Automate business and developers processes 
The project has a complicated manual flow to import some data from SharePoint reports into our database regularly. I created a lambda function that can parse the data and import it into our database. Also, I created a dedicated Jenkins job as an interface for this lambda. So the flow simplified significantly. Previously there were some stored SQL procedures that developers should trigger manually from the mysql workbench. And now, when the new report is added to SharePoint, we receive an email notification and run the Jenkins job with the required report name. Then lambda function downloads it from SharePoint, processes and loads it into MySQL database.