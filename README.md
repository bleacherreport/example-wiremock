# example-wiremock
This is an example Elastic Beanstalk environment that allows you to create a sample hello mocked URL.

### Install Elastic Beanstalk CLI and the AWS CLI
`pip install --upgrade --user awsebcli`  
`pip install --upgrade awscli`

### Create Elastic Beanstalk Environment
`eb create example-wiremock`

### Get URL of your Elastic Beanstalk Environment
`aws elasticbeanstalk describe-environments --application-name example-wiremock --environment-names example-wiremock | jq '.Environments[0].CNAME'`

Or go to the AWS console : [https://console.aws.amazon.com/elasticbeanstalk/](https://console.aws.amazon.com/elasticbeanstalk/)

### See your app running!

### Notes :
* This will create an Elastic Beanstalk application/env in the us-east-1 region
* Feel free to modify the defaults under .elasticbeanstalk/config.yml or via the console
* sysctl is tuned in ebextensions, this allows for higher network throughput for internal services.
* [Wiremock](http://wiremock.org/) is very useful for creating mocking microservice dependencies in order to test your service in isolation, and it just so happens that Elastic Beanstalk is a quick and easy way to get it up and running!

