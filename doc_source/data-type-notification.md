# Notification<a name="data-type-notification"></a>

A notification associated with a budget\. A budget can have up to five notifications\. 

Each notification must have at least one subscriber\. A notification can have one SNS subscriber and up to ten email subscribers, for a total of 11 subscribers\.

For example, if you have a budget for 200 dollars and you want to be notified when you go over 160 dollars, create a notification with the following parameters:

+ A notificationType of `ACTUAL`

+ A comparisonOperator of `GREATER_THAN`

+ A notification threshold of `80`

## Contents<a name="data-type-notification-contents"></a>

**notificationType**  
Whether the notification is for how much you have spent \(`ACTUAL`\) or for how much you are forecasted to spend \(`FORECASTED`\)\.  
Type: Enum  
Valid values: ACTUAL | FORECASTED  
Required: Yes

**comparisonOperator**  
The comparison used for this notification\.  
Type: Enum  
Valid values: GREATER\_THAN | LESS\_THAN | EQUAL\_TO  
Required: Yes

**notificationThreshold**  
The threshold associated with a notification\. AWS notifies you when you go over the threshold \(`ACTUAL` notifications\), or when you are forecasted to go over the threshold \(`FORECASTED` notifications\)\. Thresholds are always a percentage\.  
Type: Double  
Length constraints: Minimum of 0, maximum of 100\.  
Required: Yes