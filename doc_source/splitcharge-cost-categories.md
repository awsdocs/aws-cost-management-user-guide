# Splitting charges within cost categories<a name="splitcharge-cost-categories"></a>

You can use split charge rules to allocate your charges between your cost category values\. Splitting charges is useful when you have costs that aren't directly attributed to a single owner\. Therefore, the costs can't be categorized into a single cost category value\. For example, your organization has a set of costs shared by multiple teams, business units, and financial owners that incur data transfer costs, enterprise support, and operating costs\. You can define split charge rules when you create or edit your cost categories\. For more information about these processes, see [Creating cost categories](create-cost-categories.md) and [Editing cost categories](edit-cost-categories.md)\.

This is a list of terms you'll see when configuring your split charges\.

**Source**  
The group of shared costs you want to split\. Sources can be any of your existing cost category values\.

**Targets**  
The cost category values you want to split your costs across, defined by the source\.

**Allocation method**  
How you want your source costs split between your targets\. You can choose from the following methods:  
**Proportional** \- Allocates costs across your targets based on the proportional weighted cost of each target\.  
**Fixed** \- Allocates costs across your targets based on your defined allocation percentage\.  
**Even split** \- Allocates costs evenly across all targets\.

## Prerequisites<a name="splitcharge-cost-categories-prereq"></a>

Before you define your split charge rules, you must categorize your costs into the appropriate cost category values\.

**Example**  
You define a business unit view of your organization, using a `Business unit` cost category, with values `engineering`, `marketing`, and `FinOps`\. Your organization is also operating a shared infrastructure platform that supports engineering and marketing business units\.  
To allocate costs of this shared infrastructure platform to the target business unit, categorize its costs into a new cost category value, `Infrastructure Platform` using the appropriate [dimensions](manage-cost-categories.md#cost-categories-dimensions)\.

We recommend that you move your cost category values containing shared costs to the top of the rule list\. Because cost category rules are evaluated in a top\-down order, your shared costs are categorized before individual business units are categorized\. After these shared costs are categorized, they can then be split across your business units\.

## Understanding split charge best practices<a name="splitcharge-cost-categories-best"></a>

For instructions on how to configure your split charges, see [Creating cost categories](create-cost-categories.md) step 15\. After you define split charge rules, you can view the split and allocated costs on the **cost categories details** page in the console\. The details page provides an overview of your costs for each cost category value\. This includes the costs for before and after calculating the split charges\. You can also download a CSV report from the details page\.

Note the following scenarios when configuring your split charges:
+ A cost category value can be used as a source only once across all split charge rules\. This means that, if a value is used as a source, it can't be used as a target\. If the value is used as a target, it can't be used as a source\. A value can be used as a target in multiple split charge rules\.
+ If you want to use cost category values as a source or split charge target when the value was created from [inherited values](manage-cost-categories.md#cost-categories-rule-types) rules, you must wait until the [cost category status](manage-cost-categories.md#cost-categories-stat) changes to **Applied**\.
+ Split charge rules and the total allocated costs are only presented on the **cost categories details** page\. These costs do not appear and don't impact your AWS Cost and Usage Reports, Cost Explorer, and other AWS Cost Management tools\.
+ You can define up to 10 split charge rules for a cost category

For more information about cost category quotas, see [AWS Cost Categories](billing-limits.md#limits-categories)\.