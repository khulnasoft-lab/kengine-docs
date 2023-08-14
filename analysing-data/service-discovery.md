---
label: Baselime Service Discovery
order: 3
---

# Baselime Service Discovery


Baselime's Service Discovery enables you to automatically discover services in your AWS account, and organize logs, metrics, traces, and other telemetry data into services. This helps you to organize your telemetry data around services, create boundaries between services and teams, and make queries much faster.

This guide provides an overview of the Baselime Service Discovery, and how it can help you manage your serverless application more effectively.

---

## Discovering Services

Baselime automatically discovers Lambda functions, API Gateway endpoints, SQS queues, and all other serverless resources in your AWS account. Each resource is associated. The association is done through CloudFormation. All resource belonging to the same CloudFormation stack or group of stacks (if using the sst framework for example) will be grouped in the same service.

Baselime then groups the telemetry data generated by these resources into services.

You can view the list of discovered services in the Baselime dashboard, as shown in the screenshot below:

![Services list in the Baselime console](../assets/images/illustrations/analyzing-data/service-list.png)

Each service in the list provides an overview of the telemetry data that is available for that service, including logs, metrics, and traces. You can click on a service to view more detailed information about the service, such as the resources associated with the service, and query the telemetry data generated by those resources.

Services also enable you to organise your queries, alerts and dashboards within services.

---

## Querying Telemetry Data

Baselime's Service Discovery also makes querying much faster. Instead of searching through a large amount of data to find the information you need, you can query the data for a specific service. This accelerate your debugging and helps you identify issues and troubleshoot problems in your application.

## Overriding the service discovery

If you want to change the service a Cloud Formation stack creates then add a tag with the key `baselime:service`. This will take precedence over any other tags or the service name.