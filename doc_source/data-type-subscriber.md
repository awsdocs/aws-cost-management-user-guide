# Subscriber<a name="data-type-subscriber"></a>

The subscriber to a budget notification\. The subscriber consists of a subscription type and either an Amazon Simple Notification Service \(SNS\) topic or an email address\.

For example, an email subscriber would have the following parameters:

+ A `subscriptionType` of `EMAIL`

+ An `address` of `example@example.com`

## Contents<a name="data-type-subscriber-contents"></a>

**subscriptionType**  
The type of notification that AWS sends to a subscriber\.  
Type: Enum  
Valid values: SNS | EMAIL  
Required: Yes

**address**  
The address that AWS sends budget notifications to, either an SNS topic or an email\.  
Type: String  
Required: Yes