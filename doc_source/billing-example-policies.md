# AWS Billing policy examples<a name="billing-example-policies"></a>

This topic contains example policies that you can attach to your IAM user or group to control access to your account's billing information and tools\. The following basic rules apply to IAM policies for Billing and Cost Management:
+ `Version` is always `2012-10-17`\.
+ `Effect` is always `Allow` or `Deny`\.
+ `Action` is the name of the action or a wildcard \(`*`\)\. 

  The action prefix is `budgets` for AWS Budgets, `cur` for AWS Cost and Usage Reports, `aws-portal` for AWS Billing, or `ce` for Cost Explorer\.
+ `Resource` is always `*` for AWS Billing\.

  For actions that are performed on a `budget` resource, specify the budget Amazon Resource Name \(ARN\)\.
+ It's possible to have multiple statements in one policy\.

For a list of actions policies for the AWS Cost Management console, see [AWS Cost Management policy examples](https://docs.aws.amazon.com/cost-management/latest/userguide/billing-example-policies.html) in the *AWS Cost Management user guide*\.

**Note**  
These policies require that you activate IAM user access to the Billing and Cost Management console on the [Account Settings](https://console.aws.amazon.com/billing/home#/account) console page\. For more information, see [Activating access to the AWS Billing console](control-access-billing.md#ControllingAccessWebsite-Activate)\.

**Topics**
+ [Allow IAM users to view your billing information](#example-billing-view-billing-only)
+ [Allow IAM users to access the reports console page](#example-billing-view-reports)
+ [Deny IAM users access to the Billing and Cost Management consoles](#example-billing-deny-all)
+ [Deny AWS Console cost and usage widget access for member accounts](#example-billing-deny-widget)
+ [Deny AWS Console cost and usage widget access for specific IAM users and roles](#example-billing-deny-ce)
+ [Allow full access to AWS services but deny IAM users access to the Billing and Cost Management consoles](#ExampleAllowAllDenyBilling)
+ [Allow IAM users to view the Billing and Cost Management consoles except for account settings](#example-billing-read-only)
+ [Allow IAM users to modify billing information](#example-billing-deny-modifybilling)
+ [Deny access to account settings, but allow full access to all other billing and usage information](#example-billing-deny-modifyaccount)
+ [Deposit reports into an Amazon S3 bucket](#example-billing-s3-bucket)
+ [Find products and prices](#example-policy-pe-api)
+ [View costs and usage](#example-policy-ce-api)
+ [Enable and disable AWS Regions](#enable-disable-regions)
+ [View and manage cost categories](#example-policy-cc-api)
+ [Create, view, edit, or delete AWS Cost and Usage Reports](#example-policy-report-definition)
+ [View and manage purchase orders](#example-view-manage-purchaseorders)
+ [View and update the Cost Explorer preferences page](#example-view-update-ce)
+ [View, create, update, and delete using the Cost Explorer reports page](#example-view-ce-reports)
+ [View, create, update, and delete reservation and Savings Plans alerts](#example-view-ce-expiration)
+ [Allow read\-only access to AWS Cost Anomaly Detection](#example-policy-ce-ad)
+ [Allow AWS Budgets to apply IAM policies and SCPs](#example-budgets-IAM-SCP)
+ [Allow AWS Budgets to apply IAM policies and SCPs and target EC2 and RDS instances](#example-budgets-applySCP)
+ [Allow IAM users to view US tax exemptions and create AWS Support cases](#example-awstaxexemption)

## Allow IAM users to view your billing information<a name="example-billing-view-billing-only"></a>

To allow an IAM user to view your billing information without giving the IAM user access to sensitive account information, use a policy similar to the following example policy\. Such a policy prevents users from accessing your password and account activity reports\. This policy allows IAM users to view the following Billing and Cost Management console pages, without giving them access to the **Account Settings** or **Reports** console pages:
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

## Allow IAM users to access the reports console page<a name="example-billing-view-reports"></a>

To allow an IAM user to access the **Reports** console page and to view the usage reports that contain account activity information, use a policy similar to this example policy\.

For definitions of each action, see [AWS Billing actions policies](billing-permissions-ref.md#user-permissions)\.

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

## Deny IAM users access to the Billing and Cost Management consoles<a name="example-billing-deny-all"></a>

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

## Deny AWS Console cost and usage widget access for member accounts<a name="example-billing-deny-widget"></a>

To restrict member \(linked\) account access to cost and usage data, use your management \(payer\) account to access the Cost Explorer preferences tab and uncheck **Linked Account Access**\. This will deny access to cost and usage data from the Cost Explorer \(AWS Cost Management\) console, Cost Explorer API, and AWS Console Home page's cost and usage widget regardless of the IAM actions a member account’s IAM user or role has\.

## Deny AWS Console cost and usage widget access for specific IAM users and roles<a name="example-billing-deny-ce"></a>

To deny AWS Console cost and usage widget access for specific IAM users and roles, use the permissions policy below\.

**Note**  
Adding this policy to an IAM user or role will deny users access to Cost Explorer \(AWS Cost Management\) console and Cost Explorer APIs as well\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Deny",
            "Action": "ce:*",
            "Resource": "*"
        }
    ]
}
```

## Allow full access to AWS services but deny IAM users access to the Billing and Cost Management consoles<a name="ExampleAllowAllDenyBilling"></a>

To deny IAM users access to everything on the Billing and Cost Management console, use the following policy\. Deny user access to AWS Identity and Access Management \(IAM\) to prevent access to the policies that control access to billing information and tools\.

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

## Allow IAM users to view the Billing and Cost Management consoles except for account settings<a name="example-billing-read-only"></a>

This policy allows read\-only access to all of the Billing and Cost Management console\. This includes the **Payments Method** and **Reports** console pages\. However, this policy denies access to the **Account Settings** page\. This means it protects the account password, contact information, and security questions\. 

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

## Allow IAM users to modify billing information<a name="example-billing-deny-modifybilling"></a>

To allow IAM users to modify account billing information in the Billing and Cost Management console, allow IAM users to view your billing information\. The following policy example allows an IAM user to modify the **Consolidated Billing**, **Preferences**, and **Credits** console pages\. It also allows an IAM user to view the following Billing and Cost Management console pages:
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

## Deny access to account settings, but allow full access to all other billing and usage information<a name="example-billing-deny-modifyaccount"></a>

To protect your account password, contact information, and security questions, deny IAM user access to **Account Settings** while still enabling full access to the rest of the functionality in the Billing and Cost Management console\. The following is an example policy\.

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

## Deposit reports into an Amazon S3 bucket<a name="example-billing-s3-bucket"></a>

The following policy allows Billing and Cost Management to save your detailed AWS bills to an Amazon S3 bucket if you own both the AWS account and the Amazon S3 bucket\. This policy must be applied to the Amazon S3 bucket, rather than an IAM user\. This is because it's a resource\-based policy, not a user\-based policy\. We recommend that you deny IAM user access to the bucket for IAM users who don't need access to your bills\.

Replace *bucketname* with the name of your bucket\.

For more information, see [ Using Bucket Policies and User Policies](https://docs.aws.amazon.com/AmazonS3/latest/dev/using-iam-policies.html) in the *Amazon Simple Storage Service User Guide*\.

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

## Find products and prices<a name="example-policy-pe-api"></a>

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

## View costs and usage<a name="example-policy-ce-api"></a>

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

## Enable and disable AWS Regions<a name="enable-disable-regions"></a>

For an example IAM policy that allows users to enable and disable Regions, see [AWS: Allows Enabling and Disabling AWS Regions](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_examples_aws-enable-disable-regions.html) in the *IAM User Guide*\. 

## View and manage cost categories<a name="example-policy-cc-api"></a>

To allow IAM users to use, view, and manage cost categories, use the following policy to grant them access\.

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

## Create, view, edit, or delete AWS Cost and Usage Reports<a name="example-policy-report-definition"></a>

This policy allows an IAM user to create, view, edit, or delete `sample-report` using the API\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "ManageSampleReport",
            "Effect": "Allow",
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

## View and manage purchase orders<a name="example-view-manage-purchaseorders"></a>

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

## View and update the Cost Explorer preferences page<a name="example-view-update-ce"></a>

This policy allows an IAM user to view and update using the **Cost Explorer preferences page**\.

```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "VisualEditor0",
      "Effect": "Allow",
      "Action": [
        "aws-portal:ViewBilling",
        "ce:UpdatePreferences"
       ],
      "Resource": "*"
    }
  ]
}
```

The following policy allows IAM users to view Cost Explorer, but deny permission to view or edit the **Preferences** page\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "VisualEditor0",
            "Effect": "Allow",
            "Action": [
                "aws-portal:ViewBilling"
            ],
            "Resource": "*"
        },
        {
            "Sid": "VisualEditor1",
            "Effect": "Deny",
            "Action": [
                "ce:GetPreferences",
                "ce:UpdatePreferences"
            ],
            "Resource": "*"
        }
    ]
}
```

The following policy allows IAM users to view Cost Explorer, but deny permission to edit the **Preferences** page\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "VisualEditor0",
            "Effect": "Allow",
            "Action": [
                "aws-portal:ViewBilling"
            ],
            "Resource": "*"
        },
        {
            "Sid": "VisualEditor1",
            "Effect": "Deny",
            "Action": [
                "ce:UpdatePreferences"
            ],
            "Resource": "*"
        }
    ]
}
```

## View, create, update, and delete using the Cost Explorer reports page<a name="example-view-ce-reports"></a>

This policy allows an IAM user to view, create, update, and delete using the **Cost Explorer reports page**\.

```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "VisualEditor0",
      "Effect": "Allow",
      "Action": [
        "aws-portal:ViewBilling",
        "ce:CreateReport",
        "ce:UpdateReport",
        "ce:DeleteReport"
       ],
      "Resource": "*"
    }
  ]
}
```

The following policy allows IAM users to view Cost Explorer, but deny permission to view or edit the **Reports** page\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "VisualEditor0",
            "Effect": "Allow",
            "Action": [
                "aws-portal:ViewBilling"
            ],
            "Resource": "*"
        },
        {
            "Sid": "VisualEditor1",
            "Effect": "Deny",
            "Action": [
                "ce:DescribeReport",
                "ce:CreateReport",
                "ce:UpdateReport",
                "ce:DeleteReport"
            ],
            "Resource": "*"
        }
    ]
}
```

The following policy allows IAM users to view Cost Explorer, but deny permission to edit the **Reports** page\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "VisualEditor0",
            "Effect": "Allow",
            "Action": [
                "aws-portal:ViewBilling"
            ],
            "Resource": "*"
        },
        {
            "Sid": "VisualEditor1",
            "Effect": "Deny",
            "Action": [
                "ce:CreateReport",
                "ce:UpdateReport",
                "ce:DeleteReport"
            ],
            "Resource": "*"
        }
    ]
}
```

## View, create, update, and delete reservation and Savings Plans alerts<a name="example-view-ce-expiration"></a>

This policy allows an IAM user to view, create, update, and delete [reservation expiration alerts](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/ce-ris.html) and [Savings Plans alerts](https://docs.aws.amazon.com/savingsplans/latest/userguide/sp-overview.html#sp-alert)\. To edit reservation expiration alerts or Savings Plans alerts, a user needs all three granular actions: `ce:CreateNotificationSubscription`, `ce:UpdateNotificationSubscription`, and `ce:DeleteNotificationSubscription`\.

```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "VisualEditor0",
      "Effect": "Allow",
      "Action": [
        "aws-portal:ViewBilling",
        "ce:CreateNotificationSubscription",
        "ce:UpdateNotificationSubscription",
        "ce:DeleteNotificationSubscription"
       ],
      "Resource": "*"
    }
  ]
}
```

The following policy allows IAM users to view Cost Explorer, but denies permission to view or edit the **Reservation Expiration Alerts** and **Savings Plans alert** pages\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "VisualEditor0",
            "Effect": "Allow",
            "Action": [
                "aws-portal:ViewBilling"
            ],
            "Resource": "*"
        },
        {
            "Sid": "VisualEditor1",
            "Effect": "Deny",
            "Action": [
                "ce:DescribeNotificationSubscription",
                "ce:CreateNotificationSubscription",
                "ce:UpdateNotificationSubscription",
                "ce:DeleteNotificationSubscription"
            ],
            "Resource": "*"
        }
    ]
}
```

The following policy allows IAM users to view Cost Explorer, but denies permission to edit the **Reservation Expiration Alerts** and **Savings Plans alert** pages\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "VisualEditor0",
            "Effect": "Allow",
            "Action": [
                "aws-portal:ViewBilling"
            ],
            "Resource": "*"
        },
        {
            "Sid": "VisualEditor1",
            "Effect": "Deny",
            "Action": [
                "ce:CreateNotificationSubscription",
                "ce:UpdateNotificationSubscription",
                "ce:DeleteNotificationSubscription"
            ],
            "Resource": "*"
        }
    ]
}
```

## Allow read\-only access to AWS Cost Anomaly Detection<a name="example-policy-ce-ad"></a>

To allow IAM users read\-only access to AWS Cost Anomaly Detection, use the following policy to grant them access\. `ce:ProvideAnomalyFeedback` is optional as a part of the read\-only access\.

```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Action": [
        "ce:Get*"
      ],
      "Effect": "Allow",
      "Resource": "*"
    }
  ]
}
```

## Allow AWS Budgets to apply IAM policies and SCPs<a name="example-budgets-IAM-SCP"></a>

This policy allows AWS Budgets to apply IAM policies and service control policies \(SCPs\) on behalf of the user\.

```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "iam:AttachGroupPolicy",
        "iam:AttachRolePolicy",
        "iam:AttachUserPolicy",
        "iam:DetachGroupPolicy",
        "iam:DetachRolePolicy",
        "iam:DetachUserPolicy",
        "organizations:AttachPolicy",
        "organizations:DetachPolicy"
      ],
      "Resource": "*"
    }
  ]
}
```

## Allow AWS Budgets to apply IAM policies and SCPs and target EC2 and RDS instances<a name="example-budgets-applySCP"></a>

This policy allows AWS Budgets to apply IAM policies and service control policies \(SCPs\), and to target Amazon EC2 and Amazon RDS instances on behalf of the user\.

Trust policy

```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "Service": "budgets.amazonaws.com"
      },
      "Action": "sts:AssumeRole"
    }
  ]
}
```

Permissions policy

```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "ec2:DescribeInstanceStatus",
        "ec2:StartInstances",
        "ec2:StopInstances",
        "iam:AttachGroupPolicy",
        "iam:AttachRolePolicy",
        "iam:AttachUserPolicy",
        "iam:DetachGroupPolicy",
        "iam:DetachRolePolicy",
        "iam:DetachUserPolicy",
        "organizations:AttachPolicy",
        "organizations:DetachPolicy",
        "rds:DescribeDBInstances",
        "rds:StartDBInstance",
        "rds:StopDBInstance",
        "ssm:StartAutomationExecution"
      ],
      "Resource": "*"
    }
  ]
}
```

## Allow IAM users to view US tax exemptions and create AWS Support cases<a name="example-awstaxexemption"></a>

This policy allows an IAM user to view US tax exemptions and create AWS Support cases to upload exemption certificates in the tax exemption console\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Action": [
                "aws-portal:*",
                "tax:GetExemptions",
                "tax:UpdateExemptions",
                "support:CreateCase",
                "support:AddAttachmentsToSet"
            ],
            "Resource": [
                "*"
            ],
            "Effect": "Allow"
        }
    ]
}
```