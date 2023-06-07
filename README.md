# conformity-to-cloudwatch

Conformity-to-cloudwatch is an adittional feature to deploy all the required resoruces to send Cloud One Conformmity new alerts to a cloudwatch log group, using the native integration that Conformmity already has  with SNS 

# Deployment

To deploy this feature, just download the template found in the repository and deploy it to the AWS cloudformation service.

The template allows you to modify the following two parameters:

#### RetentionPeriod 

By default, CloudWatch Logs will store your log data indefinitely. You can change the retention for each Log Group at any time, 90 days is a very common time within company compliance for data retention.

#### LogName 

You can customize the  log group name where the alerts will be stored

<img width="398" alt="image" src="https://github.com/alejogaci/conformity-to-cloudwatch/assets/37232597/9dcd094f-f2aa-420e-9248-753d671eee7c">

# Outputs

- `TopicArn` SNS Topic ARN to be used in Conformity

**Note:** Save this output 

# Conformity SNS integration

Once deployed, you just have to go to conformity, select the AWS account for which you want to integrate, enter `settings` and then `Update Communication settings`, you should see something like this

<img width="524" alt="image" src="https://github.com/alejogaci/conformity-to-cloudwatch/assets/37232597/b013c8d0-2b61-4bed-aa65-79bb25193ad1">

Go to `configure` under `Amazon SNS` an then click on `Create an Amazon SNS channel` and the following window will appear

<img width="458" alt="image" src="https://github.com/alejogaci/conformity-to-cloudwatch/assets/37232597/0ec8522e-6552-4074-b883-f6b874b3776a">

**Note:** Enable at least `Automatic notifications` so that every time the bot runs, conformity sends new findings via SNS

Click on `Configure now...` , set the SNS Topic ARN and save changes

