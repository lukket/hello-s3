# Hello S3

A simple Hello World hosted on Amazon's S3.

## Requirements

* [Create AWS account](https://aws.amazon.com)
* [Install AWS CLI (version 2)](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html)
* Create IAM user with sufficient permissions (e.g., [PowerUserAccess](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_job-functions.html#jf_developer-power-user))
* [Configure AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html#cli-configure-quickstart-config)

## Create Bucket

    aws s3 mb s3://hello-s3.lukket

## Enable Static Website Hosting

    aws s3 website s3://hello-s3.lukket --index-document index.html

## Make Website Publicly Available

    aws s3api put-bucket-policy --bucket hello-s3.lukket --policy file://website-bucket-policy.json

## Upload Content

    aws s3 cp index.html s3://hello-s3.lukket/index.html

## Visit Website

    http://hello-s3.lukket.s3-website.eu-central-1.amazonaws.com/

## Clean Up

    aws s3 rm s3://hello-s3.lukket/index.html && aws s3 rb s3://hello-s3.lukket
