# New Breakpoint S4: Episode 2 - Simplify cloud-native app deployment and scaling with AKS

## How does APIM integrated with Microservices hosted in AKS?
Expose your Microservices via Ingress Controllers and then use APIM as the Gateway Facade

## Where does the app actually get deployed in cloud? how do we manage VNetPeering and private end points etc ?
Apps are containers that would be running in Pods which is the smallest unit of deployment in K8s but you use higher level constructs like deployments to deploy your Apps, Apps are exposed either via Services or ingress controllers that you may choose to be private or public.. Since AKS can be VNET integrated using CNI, you get all the capabilities of VNET peering , accessing private endpoints

## Is the interaction with AKS is through Kubectl only ? There is no UI to achieve all the interactions?
Kubectl is the CLI that interacts with the Kube API server, you can see all the K8s objects, but to create it, you need to either call the Rest APIs, use Kubernetes Dashboard (kubectl proxy) or use the SDKs available

## where would I see the deployed web apps in Azure portal? Like I can see web apps hosted on Azure Web Service under my subscription that is under a resource group. What is the hosting mechanism and lookup for AKS based service?
You can see this in the AKS Blade.

## How do we achieve high availability whole azure region failures?
AKS deployed across multiple regions with Azure Front Door or Traffic Manager

## Can we have AppGatway with WAF pointed to nginx in AKS?
Yes, you certainly can using AGIC, Application Gateway Ingress Controller

## is there an example repo for AKS that Manoj is showing where we can peek at?
The commands used here will be stored in my GH repo, check my GH Handle, @manojnair soon

## IS there a session for deployment of AKS workloads using CI/CD pipeline
If you can come to Kubernetes Community Day there are bound to be interesting sessions on the agenda: https://community.cncf.io/events/details/cncf-kcd-australia-presents-kcd-sydney-24/  Else I will make it a request for an upcoming episode


... more questions being added by EOW


