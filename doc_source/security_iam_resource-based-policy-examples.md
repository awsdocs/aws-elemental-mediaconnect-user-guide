# AWS Elemental MediaConnect Resource\-Based Policy Examples<a name="security_iam_resource-based-policy-examples"></a>

To access the AWS Elemental MediaConnect console, you must have a minimum set of permissions that allows you to list and view details about the AWS Elemental MediaConnect resources in your AWS account\. The IAM policies in this section show examples of policies that allow specific actions on resources in AWS Elemental MediaConnect\.

## Allow Read Access to All Resources in AWS Elemental MediaConnect<a name="iam-policy-examples-for-mediaconnect-actions-read-only-all-resources"></a>

To access the AWS Elemental MediaConnect console, you must have a policy that defines which actions you are allowed to take on AWS Elemental MediaConnect resources in your AWS account\. The IAM policy below provides the following permissions:
+ The section for the `mediaconnect:List*` and `mediaconnect:Describe*` actions allow read\-only access to all resources that you create in AWS Elemental MediaConnect\.
+ The section for the `ec2:DescribeAvailabilityZones` action allows the service to obtain information about which Availability Zone the flow is in\. This portion of the policy is required\.
+ The section for the `cloudwatch:GetMetricStatistics` action allows the service to obtain metrics from Amazon CloudWatch\. This portion of the policy is required\.
+ The section for the `iam:PassRole` action allows IAM to *pass* a role to AWS Elemental MediaConnect the service to communicate with IAM in order to assume a role on behalf of the service\. This allows the service to assume the role later and perform actions on your behalf\. This portion of the policy is required\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Action": [
                "mediaconnect:List*",
                "mediaconnect:Describe*"
            ],
            "Effect": "Allow",
            "Resource": "*"
        },
        {
            "Action": [
                "ec2:DescribeAvailabilityZones"
            ],
            "Effect": "Allow",
            "Resource": "*"
        },
         {
            "Action": [
                "cloudwatch:GetMetricStatistics"
            ],
            "Effect": "Allow",
            "Resource": "*"
        },
        {
            "Action": [
                "iam:PassRole"
            ],
            "Effect": "Allow",
            "Resource": "*"
        }
    ]
}
```

## Allow All AWS Elemental MediaConnect Actions on a Specific Resource<a name="iam-policy-examples-for-mediaconnect-actions-all-actions-specific-resource"></a>

Every user of AWS Elemental MediaConnect must have a policy that defines permissions on AWS Elemental MediaConnect resources\. The IAM policy below provides the following permissions:
+ The section for the `mediaconnect:*` action all AWS Elemental MediaConnect actions on a specific resource\.
+ The section for the `ec2:DescribeAvailabilityZones` action allows the service to obtain information about which Availability Zone the flow is in\. This portion of the policy is required and should apply to all resources\.
+ The section for the `cloudwatch:GetMetricStatistics` action allows the service to obtain metrics from Amazon CloudWatch\. This portion of the policy is required and should apply to all resources\.
+ The section for the `iam:PassRole` action allows IAM to *pass* a role to AWS Elemental MediaConnect the service to communicate with IAM in order to assume a role on behalf of the service\. This allows the service to assume the role later and perform actions on your behalf\. This portion of the policy is required\. It can be applied to all resources, as shown in the example below, or to a specific resource\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Action": [
                "mediaconnect:*"
            ],
            "Effect": "Allow",
            "Resource": [
                "arn:aws:mediaconnect:us-west-2:111122223333:flow:1-23aBC45dEF67hiJ8-12AbC34DE5fG:exampleFlow"
            ]
        },
        {
            "Action": [
                "ec2:DescribeAvailabilityZones"
            ],
            "Effect": "Allow",
            "Resource": "*"
        },
         {
            "Action": [
                "cloudwatch:GetMetricStatistics"
            ],
            "Effect": "Allow",
            "Resource": "*"
        },
        {
            "Action": [
                "iam:PassRole"
            ],
            "Effect": "Allow",
            "Resource": "*"
        }
    ]
}
```

## Allow All Actions on All AWS Elemental MediaConnect Resources<a name="iam-policy-examples-for-mediaconnect-actions-all-actions-all-resources"></a>

Every user of AWS Elemental MediaConnect must have a policy that defines permissions on AWS Elemental MediaConnect resources\. The IAM policy below provides the following permissions:
+ The section for the `mediaconnect:*` action allows all actions on all resources that you create in AWS Elemental MediaConnect\.
+ The section for the `ec2:DescribeAvailabilityZones` action allows the service to obtain information about which Availability Zone the flow is in\. This portion of the policy is required\.
+ The section for the `cloudwatch:GetMetricStatistics` action allows the service to obtain metrics from Amazon CloudWatch\. This portion of the policy is required\.
+ The section for the `iam:PassRole` action allows IAM to *pass* a role to AWS Elemental MediaConnect the service to communicate with IAM in order to assume a role on behalf of the service\. This allows the service to assume the role later and perform actions on your behalf\. This portion of the policy is required\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Action": [
                "mediaconnect:*"
            ],
            "Effect": "Allow",
            "Resource": "*"
        },
        {
            "Action": [
                "ec2:DescribeAvailabilityZones"
            ],
            "Effect": "Allow",
            "Resource": "*"
        },
         {
            "Action": [
                "cloudwatch:GetMetricStatistics"
            ],
            "Effect": "Allow",
            "Resource": "*"
        },
        {
            "Action": [
                "iam:PassRole"
            ],
            "Effect": "Allow",
            "Resource": "*"
        }
    ]
}
```