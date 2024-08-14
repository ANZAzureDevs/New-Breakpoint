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

## Would there be cases where pods communicate to other AKS clusters?
Yes, if you need to call services deployed in a different AKS cluster managed by a different team within the Org

## Can you give an example of a use case of a client of how they used the AKS?
A big betting website uses AKS to run its betting platform microservices, so does major retail chain

## if I wanted to do a small project like Manoj in AKS, can I do that on a free tier user? if not, around how much do I need to pay to setup a similar small project?
New Azure Users get USD200 to play with AKS or any azure services.

## I am still learning K8s, but I based from how I learned about how it works, 1 thing I realized. Setting up k8 from scratch vs. using a platform like AKS.
AKS gives you a managed K8s platform, so you dont need to worrry about using Kubeadm and installation of K8s to create a cluster, Just create a nAKS cluster and you are good to go

## Before I was practicing how to use Terraform and used a tutorial that deploys a kubernetes cluster in Azure (I think that was with AKS). Then I also tried setting up K8s scratch using my laptop. I used Kubectl and minikube. Thats where I learned about the basics of K8s..and compared it to AKS or other similar platforms, it made me realized how these platforms help the heavy lifting of setting up and managing all components of k8s like orchestration.
Absolutely! Plus the integration with other Azure Services

## Will it remember the latest version you rolled out for when the pod dies or gets recreated ?
Yes, thats the reason why we use Deployments :)

## are you using Azure CLI locally in that PS ?
Yes and you can also use Cloud Shell :)

## how do you get to Cloud Shell ?
On your Azure Portal, you will see a PowerShell like icon at the top right

## how do you pick the ingressClassName here?
I have autocompletion enabled :)  kubectl completion powershell | Out-String | Invoke-Expression

## Do we need to setup the nodes (VMs) before setting up the AKS Cluster?
No, VMSS used is completely managed by Azure

## This might be brought up later or in another session. But, how do availability zones work with AKS? I understand it can only be defined on creation. However, does it apply to all the resources? The Kubernetes cluster, virtual machine scale sets, application gateway, etc.? Then how does this work with the node pools, and nodes? Thanks
Good question, in short AKS uses VMSS behind the scenes, so the VMSS spans across AZs

## How often does the Cluster needs to be upgraded?
https://learn.microsoft.com/en-us/azure/aks/upgrade

## On what instances you use VPA vs HPA?
In most cases, you will use HPA as cloud natives app prefer horizontal scaling vs vertical one... an example would be a database container that cant be sharded so needs to scale vertically instead of horizontally

## Could you please add some insights on certificate management?
AKS manages certificates required for Kubernetes internal services and authentication, for your App Services, you can integrate with LetsEncrypt / use secrets

## When is the support to AKS Automate going to be available using Terraform?
we are working on that capability as we speak, so hopefully in the next 6 months (no promises though!)

## how does the rollback work of there are multiple interconnected services?
For that, dont rollback just the service, use Helm charts

## currently the AKS Automatic documentation is pretty sparse. can you expand on what "Enterprise ready" means in this context? would there be more documentation coming out any time soon?
It comes will everything you need with policies, guardrails and capabilities that most enterprises need to start using AKS, with regards to docs, it is still a product in preview so I would expect more to come. Updates were made available on 2nd August, so if you haven't see those you might like these -
[Quickstart: Deploy an Azure Kubernetes Service (AKS) Automatic cluster (preview)](https://learn.microsoft.com/en-us/azure/aks/learn/quick-kubernetes-automatic-deploy?pivots=azure-portal) and [What is Azure Kubernetes Service (AKS) Automatic (preview)?](https://learn.microsoft.com/en-us/azure/aks/intro-aks-automatic)

## what's your take on AGIC vs nginx? what should we consider when picking one over another?
If you already use AGW, then AGIC would be easier especially with its WAF integration

## rather than lift n shift lots of apps to IaaS ..... does this mean I can "conatinerise" my on-prem servers to AKS and I need less cores , etc as the cluster has less cores than individual legacy app server ?
You containerize your apps and not the servers that host them, AKS then orchestrates the App for you depending on what you want it to do

## I have 3 tier “app” so currently have 2 windows servers 4 cores each in different security zones, does this mean with containers I don’t have 3 windows servers of 4 cores (12 cores total) and the firewalls can be  microservices also running in AKS ?
You package your apps into Containers and containers require less resources as compared to a VM, so you only need to spec how much your containers need and setup scaling rules to take care of load

## How you differ aks with azure spring apps
Spring Apps are primarily designed for Spring Boot / Apps while AKS is a container orchestrator giving you flexibility to choose what you want to run and host, its like Tanzu vs Kubernetes

## 1. Is it possible to share - How to access/use AKS automatic service?
https://learn.microsoft.com/en-us/azure/aks/learn/quick-kubernetes-automatic-deploy?pivots=azure-portal

## Is there a way to get the metric of traffic to going to both applications over a period of time? Not to check once via the browser or another pod.
One of the things you can enable in AKS monitoring is Network Observability add-on. It helps you collect and analyse data about network traffic.

## How much time before Scale up / Scale down happens ? Can the same be configured ?
The stabilization window is a period during which the HPA waits before it scales down, to avoid rapid fluctuation in pod counts, by default its 300 seconds

## is ingress controller same as application gateway in AKS? if not, which is better?
Not quite - but they can work together. Ingress controller routes traffic based on rules defined in k8s ingress resources. App Gateway is a web traffic load balancer that enables you to manage traffic to your web app. We do have Application Gateway Ingress Controller that allows you to use App Gateway as the Ingress Controller for your clusters

## how does it has 146% of CPU? did it add more CPU itself?
When you see a CPU usage figure like 146% in the context of horizontal pod scaling in Kubernetes, it typically indicates that the CPU usage has exceeded the capacity of one CPU core.












... more questions being added by EOW


