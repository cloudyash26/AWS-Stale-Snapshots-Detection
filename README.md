# AWS-Stale-Snapshots-Detection
This Lambda function uses AWS SDK to interact with EC2 and EBS resources, identifying and deleting stale snapshots that are no longer needed. This helps reduce storage costs and improve resource utilization.

## Features
* Deletes EBS snapshots not attached to any volume.
* Deletes EBS snapshots attached to volumes not attached to running EC2 instances.
* Handles volume not found scenarios.
* Logs deletion events for auditing purposes.

## Requirements
* AWS Lambda
* Python 3.10
* AWS SDK (Boto3)
* EC2 and EBS resources

## Deployment
1. Clone this repository to your local machine.
2. Create a new Lambda function in the AWS Management Console.
3. Upload the Python code to the Lambda function.
4. Configure the Lambda function's IAM role with the necessary permissions (see below).
5. Set up a trigger for the Lambda function (e.g., scheduled event).

**IAM Permissions:**

* `ec2:DescribeSnapshots`
* `ec2:DescribeInstances`
* `ec2:DescribeVolumes`
* `ec2:DeleteSnapshot`

## Configuration
* No additional configuration is required. The Lambda function will automatically detect and delete stale EBS snapshots.

## Testing
* Test the Lambda function by manually triggering it or scheduling it to run at a specific time.
* Verify that the function is deleting stale EBS snapshots as expected.

## Troubleshooting
* Check the Lambda function's logs for errors or issues.
* Verify that the IAM role has the necessary permissions.
