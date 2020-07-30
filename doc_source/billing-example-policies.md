# Billing and Cost Management policy examples<a name="billing-example-policies"></a>

This topic contains example policies that you can attach to your IAM user or group to control access to your account's billing information and tools\. The following basic rules apply to IAM policies for Billing and Cost Management:
+ `Version` is always `2012-10-17`\.
+ `Effect` is always `Allow` or `Deny`\.
+ `Action` is the name of the action or a wildcard \(`*`\)\. 

  The action prefix is `budgets` for AWS Budgets, `cur` for AWS Cost and Usage reports, `aws-portal` for AWS Billing, or `ce` for Cost Explorer\.
+ `Resource` is always `*` for AWS Billing\.

  For actions performed on a `budget` resource, specify the budget Amazon Resource Name \(ARN\)\.
+ It's possible to have multiple statements in one policy\.

**Note**  
These policies require that you activate IAM user access to the Billing and Cost Management console on the [Account Settings](https://portal.aws.amazon.com/billing/home#/account) console page\. For more information, see [Activating access to the Billing and Cost Management console](control-access-billing.md#ControllingAccessWebsite-Activate)\.

**Example topics**
+ [Example 1: Allow IAM users to view your billing information](#example-billing-view-billing-only)
+ [Example 2: Allow IAM users to access the reports console page](#example-billing-view-reports)
+ [Example 3: Deny IAM users access to the Billing and Cost Management console](#example-billing-deny-all)
+ [Example 4: Allow full access to AWS services but deny IAM users access to the Billing and Cost Management console](#ExampleAllowAllDenyBilling)
+ [Example 5: Allow IAM users to view the Billing and Cost Management console except for account settings](#example-billing-read-only)
+ [Example 6: Allow IAM users to modify billing information](#example-billing-deny-modifybilling)
+ [Example 7: Allow IAM users to create budgets](#example-billing-allow-createbudgets)
+ [Example 8: Deny access to account settings, but allow full access to all other billing and usage information](#example-billing-deny-modifyaccount)
+ [Example 9: Deposit reports into an Amazon S3 bucket](#example-billing-s3-bucket)
+ [Example 10: Find products and prices](#example-policy-pe-api)
+ [Example 11: View costs and usage](#example-policy-ce-api)
+ [Example 12: Enable and disable AWS Regions](#enable-disable-regions)
+ [Example 13: View and manage cost categories](#example-policy-cc-api)
+ [Example 14: Create, view, edit, or delete AWS Cost and Usage Reports](#example-policy-report-definition)
+ [Example 15: View and manage purchase orders](#example-view-manage-purchaseorders)

## Example 1: Allow IAM users to view your billing information<a name="example-billing-view-billing-only"></a>

To allow an IAM user to view your billing information without giving the IAM user access to sensitive account information, such as your password and account activity reports, use a policy similar to the following example policy\. This policy allows IAM users to view the following Billing and Cost Management console pages, without giving them access to the **Account Settings** or **Reports** console pages:
+ **Dashboard**
+ **Cost Explorer**
+ **Bills**
+ **Orders and invoices**
+ **Consolidated Billing**
+ **Preferences**
+ **Credits**
+ **Advance Payment**

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": "aws-portal:ViewBilling",
            "Resource": "*"
        }
    ]
}
```

## Example 2: Allow IAM users to access the reports console page<a name="example-billing-view-reports"></a>

To allow an IAM user to access the **Reports** console page and to view the usage reports that contain account activity information, use a policy similar to this example policy\.

For definitions of each action, see [Billing actions](billing-permissions-ref.md#user-permissions)\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "aws-portal:ViewUsage",
                "aws-portal:ViewBilling",
                "cur:DescribeReportDefinitions",
                "cur:PutReportDefinition",
                "cur:DeleteReportDefinition",
                "cur:ModifyReportDefinition"
            ],
            "Resource": "*"
        }
    ]
}
```

## Example 3: Deny IAM users access to the Billing and Cost Management console<a name="example-billing-deny-all"></a>

To explicitly deny an IAM user access to the all Billing and Cost Management console pages, use a policy similar to this example policy\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Deny",
            "Action": "aws-portal:*",
            "Resource": "*"
        }
    ]
}
```

## Example 4: Allow full access to AWS services but deny IAM users access to the Billing and Cost Management console<a name="ExampleAllowAllDenyBilling"></a>

To deny IAM users access to everything on the Billing and Cost Management console, use the following policy\. In this case, you should also deny user access to AWS Identity and Access Management \(IAM\) so that the users can't access the policies that control access to billing information and tools\.

**Important**  
This policy doesn't allow any actions\. Use this policy in combination with other policies that allow specific actions\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Deny",
            "Action": [
                "aws-portal:*",
                "iam:*"
            ],
            "Resource": "*"
        }
    ]
}
```

## Example 5: Allow IAM users to view the Billing and Cost Management console except for account settings<a name="example-billing-read-only"></a>

This policy allows read\-only access to all of the Billing and Cost Management console, including the **Payments Method** and **Reports** console pages, but denies access to the **Account Settings** page, thus protecting the account password, contact information, and security questions\. 

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": "aws-portal:View*",
            "Resource": "*"
        },
        {
            "Effect": "Deny",
            "Action": "aws-portal:*Account",
            "Resource": "*"
        }
    ]
}
```

## Example 6: Allow IAM users to modify billing information<a name="example-billing-deny-modifybilling"></a>

To allow IAM users to modify account billing information in the Billing and Cost Management console, you must also allow IAM users to view your billing information\. The following policy example allows an IAM user to modify the **Consolidated Billing**, **Preferences**, and **Credits** console pages\. It also allows an IAM user to view the following Billing and Cost Management console pages:
+ **Dashboard**
+ **Cost Explorer**
+ **Bills**
+ **Orders and invoices**
+ **Advance Payment**

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": "aws-portal:*Billing",
            "Resource": "*"
        }
    ]
}
```

## Example 7: Allow IAM users to create budgets<a name="example-billing-allow-createbudgets"></a>

To allow IAM users to create budgets in the Billing and Cost Management console, you must also allow IAM users to view your billing information, create CloudWatch alarms, and create Amazon SNS notifications\. The following policy example allows an IAM user to modify the **Budget** console page\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "Stmt1435216493000",
            "Effect": "Allow",
            "Action": [
                "aws-portal:ViewBilling",
                "aws-portal:ModifyBilling",
                "budgets:ViewBudget",
                "budgets:ModifyBudget"
            ],
            "Resource": [
                "*"
            ]
        },
        {
            "Sid": "Stmt1435216514000",
            "Effect": "Allow",
            "Action": [
                "cloudwatch:*"
            ],
            "Resource": [
                "*"
            ]
        },
        {
            "Sid": "Stmt1435216552000",
            "Effect": "Allow",
            "Action": [
                "sns:*"
            ],
            "Resource": [
                "arn:aws:sns:us-east-1"
            ]
        }
    ]
}
```

## Example 8: Deny access to account settings, but allow full access to all other billing and usage information<a name="example-billing-deny-modifyaccount"></a>

To protect your account password, contact information, and security questions, you can deny IAM user access to **Account Settings** while still enabling full access to the rest of the functionality in the Billing and Cost Management console, as shown in the following example\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "aws-portal:*Billing",
                "aws-portal:*Usage",
                "aws-portal:*PaymentMethods"
            ],
            "Resource": "*"
        },
        {
            "Effect": "Deny",
            "Action": "aws-portal:*Account",
            "Resource": "*"
        }
    ]
}
```

## Example 9: Deposit reports into an Amazon S3 bucket<a name="example-billing-s3-bucket"></a>

The following policy allows Billing and Cost Management to save your detailed AWS bills to an Amazon S3 bucket, as long as you own both the AWS account and the Amazon S3 bucket\. Note that this policy must be applied to the Amazon S3 bucket, instead of to an IAM user\. That is, it's a resource\-based policy, not a user\-based policy\. You should deny IAM user access to the bucket for IAM users who don't need access to your bills\.

Replace *bucketname* with the name of your bucket\.

For more information, see [ Using Bucket Policies and User Policies](https://docs.aws.amazon.com/AmazonS3/latest/dev/using-iam-policies.html)\.

```
{
  "Version": "2012-10-17",
  "Statement": [
  {
    "Effect": "Allow",
    "Principal": {
      "Service": "billingreports.amazonaws.com"
    },
    "Action": [
      "s3:GetBucketAcl",
      "s3:GetBucketPolicy"
    ],
    "Resource": "arn:aws:s3:::bucketname"
  },
  {
    "Effect": "Allow",
    "Principal": {
      "Service": "billingreports.amazonaws.com"
    },
    "Action": "s3:PutObject",
    "Resource": "arn:aws:s3:::bucketname/*"
  }
  ]
}
```

## Example 10: Find products and prices<a name="example-policy-pe-api"></a>

To allow an IAM user to use the AWS Price List Service API, use the following policy to grant them access\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "pricing:DescribeServices",
                "pricing:GetAttributeValues",
                "pricing:GetProducts"
            ],
            "Resource": [
                "*"
            ]
        }
    ]
}
```

## Example 11: View costs and usage<a name="example-policy-ce-api"></a>

To allow IAM users to use the AWS Cost Explorer API, use the following policy to grant them access\.

```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "ce:*"
      ],
      "Resource": [
        "*"
      ]
    }
  ]
}
```

## Example 12: Enable and disable AWS Regions<a name="enable-disable-regions"></a>

For an example IAM policy that allows users to enable and disable Regions, see [AWS: Allows Enabling and Disabling AWS Regions](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_examples_aws-enable-disable-regions.html) in the *IAM User Guide*\. 

## Example 13: View and manage cost categories<a name="example-policy-cc-api"></a>

To allow IAM users to use, view, and manage Cost Categories, use the following policy to grant them access\.

```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "VisualEditor0",
      "Effect": "Allow",
      "Action": [
        "aws-portal:ViewBilling",
        "ce:DescribeCostCategoryDefinition",
        "ce:UpdateCostCategoryDefinition",
        "ce:CreateCostCategoryDefinition",
        "ce:DeleteCostCategoryDefinition",
        "ce:ListCostCategoryDefinitions",
        "pricing:DescribeServices"
      ],
      "Resource": "*"
    }
  ]
}
```

## Example 14: Create, view, edit, or delete AWS Cost and Usage Reports<a name="example-policy-report-definition"></a>

This policy allows an IAM user to create, view, edit, or delete `sample-report` using the API\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "ManageSampleReport",
            "Action": [
                "cur:PutReportDefinition", 
                "cur:DeleteReportDefinition",
                "cur:ModifyReportDefinition"
            ],
            "Resource": "arn:aws:cur:*:123456789012:definition/sample-report"
        },
        {
            "Sid": "DescribeReportDefs",
            "Effect": "Allow",
            "Action": "cur:DescribeReportDefinitions",
            "Resource": "*"
        }
    ]
}
```

## Example 15: View and manage purchase orders<a name="example-view-manage-purchaseorders"></a>

This policy allows an IAM user to view and manage purchase orders, using the following policy to grant access\.

```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "VisualEditor0",
      "Effect": "Allow",
      "Action": [
        "aws-portal:ViewBilling",
        "purchase-orders:ViewPurchaseOrders",
        "purchase-orders:ModifyPurchaseOrders"
      ],
      "Resource": "*"
    }
  ]
}
```