## 2022-06-09 - Series 2 - Episode 10: Stop worrying about Kubernetes with Azure Container Apps and Dapr - Q&A

During the live session we did a live Q&A spot where attendees could ask questions. If you didn't manage to make it along, here are the ones that came up. We've included answers where possible.

### ❔ I am having problems where jobs on K8s getting mysteriously killed and am wondering if Container Apps may mean my job would run more reliably?

Moving the workload to Azure Container Apps may not solve your issue. You would need to do a root cause analysis of why the container / pod / node is being terminated today and remediate that.  If you are running on Azure Kubernetes Service and have Container Insights enabled you can use that path to try and find the cause of your issue.

### ❔ What is the main difference between Azure Container Apps and Azure Container Instances?

Container Instances are great a burstable resource via Virtual Kubelet for Kuberentes clusters, but on their own they don't have many of the features that Container Apps do. You have no native support for Dapr, no auto-scale capabilities, nor the ability to use Revisions to control the release of multiple versions of your containerised workload. You can check out [Microsoft Docs](https://docs.microsoft.com/azure/container-apps/compare-options#azure-container-instances) for more detail on this question as well.

### ❔Can I run or migrate a Windows Service to run on Container Apps?

You would need to look at rewriting the Service so that it can run as a Linux application (consider using .NET 6). Without knowing the trigger for your Service (i.e. is it reading data from a database on a schedule, or is it processing queue messages) it's hard to say where the right fit for it would be. The bottom line is there isn't a "lift and shift" option for this in Container Apps. There is no Windows Container support in Container Apps, and even if there were, it's unlikely that running in Container Apps, in the absence of any other code / solution, would make a lot of sense.

You might also want to look at the Microsoft Docs guide on [deploying a background processing application with Azure Container Apps](https://docs.microsoft.com/azure/container-apps/background-processing?tabs=bash)

### ❔ Is Container Apps the equivalent of AWS Fargate?

There are some similarities between the two services, but we feel that Azure Container Apps represents a more straight-forward approach to running microservices solutions on Kubernetes without actually needing to know Kubernetes. Fargate doesn't provide out-of-the-box support (at time of writing) for either KEDA or Dapr, and requires `Task` definitions to be in a custom JSON format. [Multi-container deployments](https://docs.microsoft.com/azure/container-instances/container-instances-multi-container-yaml) are also a native capability in Azure Container Apps.

### ❔ What are key decision points when choosing between deploying a new container app to an existing container app environment, or creating a new container app environment for the app? 

 It boils down the scope of change you're making. If you have a large number of breaking changes across containers being deployed you may want to consider a new Container App Environment, but I'd suggest you can use Revisions in a single Container App in almost all cases. 

### ❔Will you cover ingress WAF and also managed identity?

 We didn't cover this during the main session. You can find more information on using Managed Identities with Azure Container Apps on [Microsoft Docs](https://docs.microsoft.com/azure/container-apps/managed-identity). The in-built HTTP ingress controller (based on envoy proxy) doesn't have in-built WAF capabilities, so if you need that you would need to route traffic via either an [Azure Application Gateway](https://docs.microsoft.com/azure/application-gateway/overview) or [Azure Front Door](https://docs.microsoft.com/azure/frontdoor/front-door-overview).


### ❔What are the resource limitations for container apps? e.g. Startup time limitations, CPU, Memory, Storage

The Azure Container Apps service utilises standard Azure compute though we don't expose the definitions for Container Apps users today. You can find the quota information for Container Apps on [Microsoft Docs](https://docs.microsoft.com/azure/container-apps/quotas).

###  Azure functions and Azure App services both allow us to specify docker containers as the application to run. If i want to run docker containers, what are the decision points between functions, app services and container apps?

You can check out [Microsoft Docs](https://docs.microsoft.com/azure/container-apps/compare-options#azure-container-instances) for more detail that covers this question.

### ❔In terms of resiliency - can it span AZs and regions?

Container Apps supports Azure Availability Zones by default. If you want multi-Region you would need to run multiple Container Environments and then determine how they operate together. We have [DR documentation on Microsoft Docs](https://docs.microsoft.com/azure/container-apps/disaster-recovery) that is worth reviewing.

### ❔ When saying "dapr can do publish subscribe", does that mean it solves problems like "exactly once in order delivery"? Ie, does it handle the complex logic of publish subscribe, or does it just say "yeah I have a Publish() method"?

Dapr only supports "at least once" out of the box. "Exactly once" is really reliant on the underlying transport. Check out the [DAPR documentation on pub/sub](https://docs.dapr.io/developing-applications/building-blocks/pubsub/pubsub-overview/) for additional details.

### ❔ Is DAPR still in Alpha/Beta?

Dapr is production-ready since 2021.