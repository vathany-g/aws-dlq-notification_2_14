# aws-dlq-notification_2_14
Does SNS guarantee exactly once delivery to subscribers?
Amazon SNS (Simple Notification Service) does not guarantee exactly-once delivery. It guarantees "at least once" delivery to subscribers. This means that a message may be delivered more than once to a subscriber in rare cases.

What is the purpose of the Dead-letter Queue (DLQ)?
A Dead-letter Queue (DLQ) is used to handle messages that could not be successfully processed or delivered. It serves as a secondary queue where failed messages are sent, allowing for further analysis or retry logic without losing data.

How would you enable a notification to your email when messages are added to the DLQ?

Create an SNS topic and subscribe our email to it.
Set up an event source in AWS Lambda to trigger the function when messages are added to the DLQ.
Configure the Lambda function to publish a message to the SNS topic with details about the failed messages.
