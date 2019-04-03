# Authentication and Access Control for AWS Elemental MediaConnect<a name="auth-and-access-control"></a>

AWS Identity and Access Management \(IAM\) is an AWS service that helps an administrator securely control access to AWS Elemental MediaConnect resources\. Administrators use IAM to control who is *authenticated* \(signed in\) and *authorized* \(has permissions\) to use AWS Elemental MediaConnect resources\. IAM is a feature of your AWS account offered at no additional charge\.

**Topics**
+ [Introduction to Authorization and Access Control](#auth_access_introduction)
+ [Permissions Required](#auth_access_required-permissions)
+ [Understanding How AWS Elemental MediaConnect Works with IAM](#auth_access_service-with-iam)
+ [Troubleshooting Authentication and Access Control](#auth_access_troubleshoot)

## Introduction to Authorization and Access Control<a name="auth_access_introduction"></a>

**Authentication** – To sign in to AWS, you must use root user credentials \(not recommended\), IAM user credentials, or temporary credentials using IAM roles\. To learn more about these entities, see [What is Authentication?](auth_access_what-is-authentication.md)\.

**Access Control** – AWS administrators use policies to control access to AWS resources, such as the AWS Elemental MediaConnect output\. To learn more, see [What is Access Control?](auth_access_what-is-access-control.md) and [What are Policies?](auth_access_what-are-policies.md)\.

**Important**  
All resources in an account are owned by the account, regardless of who created those resources\. You must be granted access to create a resource\. However, just because you created a resource does not mean that you automatically have full access to that resource\. An administrator must explicitly grant permissions for each action that you want to perform\. That administrator can also revoke your permissions at any time\.

To help you understand the basics of how IAM works, review the following terms:
+ **Resources** – AWS services, such as AWS Elemental MediaConnect and IAM, are made up of objects called resources\. You can create, manage, and delete these resources from the service\. IAM resources include users, groups, roles, and policies\. 
  + **Users** – An IAM user represents the person or application who uses its credentials to interact with AWS\. A user consists of a name, a password to sign into the AWS Management Console, and up to two access keys that can be used with the AWS CLI or AWS API\.
  + **Groups** – An IAM group is a collection of IAM users\. You can use groups to specify permissions for its member users\. This makes it easier for you to manage permissions for multiple users\.
  + **Roles** – An IAM role does not have any long\-term credentials \(password or access keys\) associated with it\. A role can be assumed by anyone who needs it and has permissions\. An IAM user can assume a role to temporarily take on different permissions for a specific task\. Federated users can assume a role by using an external identity provider that is mapped to the role\. Some AWS services can assume a *service role* to access AWS resources on your behalf\.
  + **Policies** – Policies are JSON policy documents that define the permissions for the object to which they are attached\. AWS supports *identity\-based policies* that you attach to identities \(users, groups, or roles\)\. Some AWS services allow you to attach *resource\-based policies* to resources to control what a principal \(person or application\) can do to that resource\. AWS Elemental MediaConnect does not support resource\-based policies\.
+ **Identities** – Identities are IAM resources for which you can define permissions\. These include users, groups, and roles\.
+ **Entities** – Entities are IAM resources that you use for authentication\. These include users and roles\. 
+ **Principals** – In AWS, a principal is a person or application that uses an entity to sign in and make requests to AWS\. As a principal, you can use the AWS Management Console, the AWS CLI, or the AWS API to perform an operation \(such as deleting an output\)\. This creates a *request* for that operation\. Your request specifies the *action*, *resource*, *principal*, *principal account*, and any additional information about your request\. All of this information provides AWS with *context* for your request\. AWS checks all the policies that apply to the context of your request\. AWS authorizes the request only if each part of your request is allowed by the policies\. 

To view a diagram of the authentication and access control process, see [Understanding How IAM Works](https://docs.aws.amazon.com/IAM/latest/UserGuide/intro-structure.html) in the *IAM User Guide*\. For details about how AWS determines whether a request is allowed, see [Policy Evaluation Logic](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_evaluation-logic.html) in the *IAM User Guide*\.

## Permissions Required<a name="auth_access_required-permissions"></a>

To use AWS Elemental MediaConnect or to manage authorization and access control for yourself or others, you must have the correct permissions\. 

### Permissions Required to Use the AWS Elemental MediaConnect Console<a name="auth_access_required-permissions-console"></a>

To access the AWS Elemental MediaConnect console, you must have a minimum set of permissions that allows you to list and view details about the AWS Elemental MediaConnect resources in your AWS account\. If you create an identity\-based permissions policy that is more restrictive than the minimum required permissions, the console won't function as intended for entities with that policy\.

To ensure that those entities can still use the AWS Elemental MediaConnect console, also attach the following AWS managed policy to the user, as described in [Creating Policies on the JSON Tab](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_create.html#access_policies_create-json-editor):

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

You don't need to allow minimum console permissions for users that are making calls only to the AWS CLI or the AWS API\. Instead, you need only the permissions that match the API operation you're trying to perform\.

### Permissions Required for Authentication Management<a name="auth_access_required-permissions-iam-auth"></a>

To manage your own credentials, such as your password, access keys, and multi\-factor authentication \(MFA\) devices, your administrator must grant you the required permissions\. 

As an AWS administrator, you need full access to IAM so that you can create and manage users, groups, roles, and policies in IAM\. You should use the [AdministratorAccess](https://console.aws.amazon.com/iam/home#/policies/arn:aws:iam::aws:policy/AdministratorAccess) AWS managed policy that includes full access to all of AWS\. This policy does not provide access to the AWS Billing and Cost Management console or allow tasks that require root user credentials\. For more information, see [AWS Tasks That Require AWS Account Root User Credentials](https://docs.aws.amazon.com/general/latest/gr/aws_tasks-that-require-root.html) in the *AWS General Reference*\.

**Warning**  
Only an administrator user should have full access to AWS\. Anyone with this policy has permission to fully manage authentication and access control, in addition to modifying every resource in AWS\. To learn how to create this user, see [Create your IAM Admin User](setting-up-IAM-admin-user.md)\.

### Permissions Required for Access Control<a name="auth_access_required-permissions-iam-authz"></a>

If your administrator provided you with IAM user credentials, they attached policies to your IAM user to control what resources you can access\. To view the policies attached to your user in the AWS Management Console, you must have the following permissions:

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "ViewOwnUserInfo",
            "Effect": "Allow",
            "Action": [
                "iam:GetUserPolicy",
                "iam:ListGroupsForUser",
                "iam:ListAttachedUserPolicies",
                "iam:ListUserPolicies",
                "iam:GetUser"
            ],
            "Resource": [
                "arn:aws:iam::*:user/${aws:username}"
            ]
        },
        {
            "Sid": "ListUsersViewGroupsAndPolicies",
            "Effect": "Allow",
            "Action": [
                "iam:GetGroupPolicy",
                "iam:GetPolicyVersion",
                "iam:GetPolicy",
                "iam:ListAttachedGroupPolicies",
                "iam:ListGroupPolicies",
                "iam:ListPolicyVersions",
                "iam:ListPolicies",
                "iam:ListUsers"
            ],
            "Resource": "*"
        }
    ]
}
```

If you need additional permissions, ask your administrator to update your policies to allow you to access the actions that you require\.

## Understanding How AWS Elemental MediaConnect Works with IAM<a name="auth_access_service-with-iam"></a>

Services can work with IAM in several ways:
+ **Actions** – AWS Elemental MediaConnect supports using actions in a policy\. This allows an administrator to control whether an entity can complete an operation in AWS Elemental MediaConnect\. For example, to allow an entity to view update an output on a flow by performing the `UpdateFlowOutput` AWS API operation, an administrator must attach a policy that allows the `iam:UpdateFlowOutput` action\. 
+ **Resource\-level permissions** – AWS Elemental MediaConnect supports resource\-level permissions\. Resource\-level permissions allow you to use [ARNs](https://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html) to specify individual resources in the policy\.  Although AWS Elemental MediaConnect supports this feature, some individual actions, such as `List*` actions, do not support specifying an ARN because they are designed to return multiple resources\.
+ **Resource\-based policies** – AWS Elemental MediaConnect does not support resource\-based policies\. Resource\-based policies allow you to attach a policy to a resource within the service\. Resource\-based policies include a `Principal` element to specify which IAM identities can access that resource\. 
+ **Authorization based on tags** – AWS Elemental MediaConnect does not support authorization\-based tags\. This feature allows you to use [resource tags](https://docs.aws.amazon.com/awsconsolehelpdocs/latest/gsg/tag-editor.html) in the condition of a policy\.  For example, you might create a policy that allows tag owners full access to Amazon RDS resources that they have tagged\. You do this by using a condition key such as `rds:db-tag/Owner`\.
+ **Temporary credentials** – AWS Elemental MediaConnect supports temporary credentials\. This feature allows you to sign in with federation, assume an IAM role, or to assume a cross\-account role\. You obtain temporary security credentials by calling AWS STS API operations such as [AssumeRole](https://docs.aws.amazon.com/STS/latest/APIReference/API_AssumeRole.html) or [GetFederationToken](https://docs.aws.amazon.com/STS/latest/APIReference/API_GetFederationToken.html)\. 
+ **Service\-linked roles** – AWS Elemental MediaConnect does not support service roles\. This feature allows a service to assume a [service\-linked role](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_terms-and-concepts.html#iam-term-service-linked-role) on your behalf\. This role allows the service to access resources in other services to complete an action on your behalf\. Service\-linked roles appear in your IAM account, and are owned by the service\. An IAM administrator can view, but not edit the permissions for service\-linked roles\.
+ **Service roles** – AWS Elemental MediaConnect does not support service roles\. This feature allows a service to assume a [service role](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_terms-and-concepts.html#iam-term-service-role) on your behalf\. This role allows the service to access resources in other services to complete an action on your behalf\. Service roles appear in your IAM account, and are owned by the account\. This means that an IAM administrator can change the permissions for this role\. However, this might break the functionality of the service\.

## Troubleshooting Authentication and Access Control<a name="auth_access_troubleshoot"></a>

Use the following information to help you diagnose and fix common issues that you might encounter when working with IAM\.

**Topics**
+ [I am not authorized to perform an action in AWS Elemental MediaConnect](#auth_access_troubleshoot-no-permissions)
+ [I'm an administrator and want to allow others to access AWS Elemental MediaConnect](#auth_access_troubleshoot-admin-allow-access)
+ [I want to understand IAM without becoming an expert](#auth_access_troubleshoot-iam-expert)

### I am not authorized to perform an action in AWS Elemental MediaConnect<a name="auth_access_troubleshoot-no-permissions"></a>

If you receive an error in the AWS Management Console that tells you that you're not authorized to perform an action, then you must contact the administrator that provided you with your user name and password\. 

The following example error occurs when an IAM user named my\-user\-name tries to use the console to perform the AddFlowOutput action, but does not have permissions\.

```
User: arn:aws:iam::123456789012:user/my-user-name is not authorized to perform: MediaConnect:AddFlowOutput on resource: my-example-output
```

For this example, ask your administrator to update your policies to allow you to access the `my-example-output` resource using the `MediaConnect:AddFlowOutput` action\.

### I'm an administrator and want to allow others to access AWS Elemental MediaConnect<a name="auth_access_troubleshoot-admin-allow-access"></a>

To allow others to access AWS Elemental MediaConnect, you must create an IAM entity \(user or role\) for the person or application that needs access\. They will use the credentials for that entity to access AWS\. You must then attach a policy to the entity that grants them the correct permissions in AWS Elemental MediaConnect\. 

### I want to understand IAM without becoming an expert<a name="auth_access_troubleshoot-iam-expert"></a>

To learn more about IAM terms, concepts, and procedures, see the following pages:
+ [What is Authentication?](auth_access_what-is-authentication.md)
+ [What is Access Control?](auth_access_what-is-access-control.md)
+ [What are Policies?](auth_access_what-are-policies.md)