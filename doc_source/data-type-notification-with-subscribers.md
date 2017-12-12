# NotificationWithsubscribers<a name="data-type-notification-with-subscribers"></a>

A notification with subscribers\. A notification can have one SNS subscriber and up to ten email subscribers, for a total of 11 subscribers\.

## Contents<a name="data-type-notification-with-subscribers-contents"></a>

**notification**  
The notification associated with a budget\.  
Type: [Notification](data-type-notification.md) object  
Required: Yes

**subscribers**  
A list of subscribers who are subscribed to this notification\.  
Type: List of [Subscriber](data-type-subscriber.md) objects  
Required: Yes