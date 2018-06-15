## DEPRECATED - no longer maintained
This app used to be used in [smoke tests](https://github.com/pivotal-cf/cf-rabbitmq-smoke-tests), but it is no longer used or maintained. 


```
gradle build
cf create-service p-rabbitmq standard rabbitmq
cf create-security-group rabbitmq-sg asg-rabbitmq.json
cf bind-security-group rabbitmq-sg pcf-rabbitmq pcf-rabbitmq
cf push
curl -X POST http://pivotal-rabbitmq.bosh-lite.com/queues/<queueName> -d "the message contents" -H "content-type: text/plain"
curl -X GET http://pivotal-rabbitmq.bosh-lite.com/queues/<queueName>
cf delete-security-group rabbitmq-sg
```
