# Cloudformation RDS

## Introduction
This is the Cloud formation template to configure RDS Database with MultiAZ enabled/disabled based on input parameters
  This sets up credentials in AWS Secret Manager, which rotate every 30 days by default
  Contains logging for slow query, error queries, general logs
Specifics of each parameter are part of the description.
The subnets provided must be in the same VPC and must be from atlesat 2 AZs.
The PubliclyAccessible parameter to the db instance is set to true by default - if setting up in private subnets and accessing with a bastion, this can be disabled.

## Resources
The major resources it sets up are - 
RDS Instance
RDS Read Replica (if required)
Secret for holding DB Credentials - Rotation lambda for the same
Encryption (if required) - this requires a t3.medium or higher instance

## Execution video
Refer: https://drive.google.com/file/d/1qZo5YRVPGLOHiP1F69ettiaCvsUK3dnD/view?usp=sharing