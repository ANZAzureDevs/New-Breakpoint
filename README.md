![new breakpoint logo](media/new-breakpoint.PNG 'new breakpoint logo')

New Breakpoint is a regular online show for Australian and New Zealand developers produced by local developers at Microsoft and in the community.

This repository hosts useful follow ups, links and other information from each episode.

We want everyone who comes along to feel welcome and safe. Please make sure to review our [Code of Conduct](https://learn.microsoft.com/legal/learnevents/codeofconduct) before joining in and contributing to our discussion.

You can watch all our episodes via playlists on Microsoft ANZ's YouTube Channel - [Season 1](https://aka.ms/new-breakpoint/s1) | [Season 2](https://aka.ms/new-breakpoint/s2).

We would like to acknowledge that we record the show on the traditional lands of the Gadigal people of the Eora nation, and have guests from around Australia who join us from the traditional lands of their local people. We pay our respects to Elders past, present and future.

***

## 2023-03-01: From concept to reality: Aussie social payments fintech HelpPay’s journey

You can catch this episode on our [YouTube Channel](https://aka.ms/new-breakpoint/s2). 

What if you had a fantastic idea that gave people a way to allow others to chip in towards their bills? How do you get started turning that idea into a funded and sustainable business, all the while building the technology foundation to make the idea a reality? 

In this episode we have co-founder of HelpPay, [Andrew Ellett](https://www.linkedin.com/in/andrewellett/), and partner company Revium’s Technical Director[Jacques Botes](https://www.linkedin.com/in/jacquesbot/) joining us to talk about their journey from concept to functioning business. If you are a developer wondering how to bootstrap your business, or the technical founder of a business, then this is a great episode to tune in for.

Learn more about HelpPay through these channels:
- Website: https://www.helppay.com.au/ 
  - https://helppay.com.au/stories - Our news stories feature in alpha release to allow people to publicly get help on our website
- LinkedIn: https://www.linkedin.com/company/helppay-au/ - LinkedIn
-	Facebook: https://www.facebook.com/HelpPay - Facebook
    - Helping group: https://www.facebook.com/groups/463062602331726 – for people to publicly post bills and ask or give help
- Instagram: https://www.instagram.com/helppay.au/

Andrew shared some tips on purpose and "slicing the pie", here are some good links:

- Simon Sinek (on Purpose): https://www.youtube.com/channel/UCPmfPl-BsCd3wmE8i45LAoA
- Slicing the Pie for equity: https://www.vestd.com/blog/slicing-pie-a-tasty-way-to-share-equity

Jacques covered a range of topics on Azure and Microsoft's startup benefits:

- Microsoft for Startups: https://www.microsoft.com/startups
- Azure Architecture guide: https://learn.microsoft.com/azure/architecture/
- Azure API Management: 
  - Key concepts: https://learn.microsoft.com/azure/api-management/api-management-key-concepts
  - Developer Portal feature: https://learn.microsoft.com/azure/api-management/api-management-howto-developer-portal
- Azure Form Recognizer
  - Overview: https://learn.microsoft.com/azure/applied-ai-services/form-recognizer/overview?view=form-recog-3.0.0
  - Example architecture: https://learn.microsoft.com/azure/architecture/example-scenario/ai/automate-document-processing-azure-form-recognizer


If you enjoyed the episode and want more content like it? Try our monthly developer newsletter: https://aka.ms/DevNewsletterJoin

***

## 2023-02-16: Hey, GitHub! What’s new in the world of GitHub with Damian Brady

If you missed the live show you can catch the episode on [YouTube](https://youtu.be/ZGJQ8V8nefM). 

There were a lot of announcements at GitHub Universe 2022, from free Codespaces for everyone, a new GitHub Actions Importer tool, improved security tooling, better project planning tools, and event support for careers in open source!

This episode we had Head of Developer Advocacy at GitHub - [Damian Brady](http://twitter.com/damovisa) walk through some of these announcements including some a cool demo of using Stable Diffusion in a Codespace. 

Want to learn more? Here are some great next steps:

-	Major announcements summary of GitHub Universe - https://github.blog/2022-11-09-everything-new-from-github-universe-2022/
- Research on use / non-use of copilot - https://github.blog/2022-09-07-research-quantifying-github-copilots-impact-on-developer-productivity-and-happiness/. 
  - Also this one if you'd prefer a fun video: https://www.youtube.com/watch?v=jr38-yiTr8k
-	GitHub Next - https://githubnext.com
-	GitHub Projects - https://github.com/features/issues
- GitHub Actions:
  - Large Runners - https://github.blog/changelog/2022-09-01-github-actions-larger-runners-are-now-in-public-beta/
  - Importer - https://github.blog/changelog/2022-11-16-introducing-github-actions-importer/
  - ARM Virtual Hardware - https://resources.github.com/devops/actions/arm-virtual-hardware/
  - Required workflows and configuration variables - https://github.blog/2023-01-10-introducing-required-workflows-and-configuration-variables-to-github-actions/
  - Required workflows docs (read about exclusions, etc): https://docs.github.com/en/actions/using-workflows/required-workflows
- GitHub Security - private vulnerability reporting - https://github.blog/changelog/2022-11-09-privately-report-vulnerabilities-to-repository-maintainers/
- Career and business development:
	- Open source career accelerator - https://accelerator.github.com/
  - M12 GitHub Fund - https://m12.vc/news/announcing-the-m12-github-fund/
- GitHub Codespaces:
  - Codespaces for everyone - https://github.blog/2022-11-10-whats-new-with-codespaces-from-github-universe-2022/
  - Jupyter Notebooks in Codespaces - Jupyter Lab - https://github.blog/changelog/2022-11-09-using-codespaces-with-jupyterlab-public-beta/

If you enjoyed the episode and want more content like it? Try our monthly developer newsletter: https://aka.ms/DevNewsletterJoin

### Q&A segment

- Question: GitHub Actions: with required workflows, can say a .net specific workflow automatically skip a NodeJS repo

  Answer: Yes, you would need to set that required workflow for those repositories specifically though.

- Question: GitHub Codespaces: If you had multiple repos that need to integrate with each other say via APIs - Is it possible to have Codespace A hit an API endpoint in Codespace B?

  Answer: Within a Codespace, you are able to open ports and specify whether they're open publicly, to the organization (so you can connect if you have the other Codespace open), or keep them private.

***

## 2022-11-22: A GitOps approach to multi-microservice and environment apps with Azure Red Hat OpenShift

If you missed the live show you can catch the episode on [YouTube](https://youtu.be/SwSd85866NY). You can also check out the [episode Q&A page](qanda/S02E12LiveQandA.md).

Microservices assist in rapidly building and deploying distributed apps. But, with a distributed system comes added complexity. As your microservices grow, the headache of managing their environmental configuration can too – unless you get ahead of it.  

With Azure Red Hat OpenShift (ARO), you can take a GitOps approach to managing the lifecycle of your Kubernetes platform and apps.  

In this episode of New Breakpoint, [Paul Foster](https://www.linkedin.com/in/paul-foster-5751917/) from Red Hat ran us through how to configure a production-grade Kubernetes ecosystem in a day – powered by ARO and GitOps with Tekton, CI/CD and Istio using familiar tools such as Helm.  

Want to learn more? Here are some great next steps:

- OpenShift GitOps: https://docs.openshift.com/container-platform/4.11/cicd/gitops/understanding-openshift-gitops.html
  - Upstream project - ArgoCD: https://argo-cd.readthedocs.io/en/stable/
- OpenShift Pipelines: https://docs.openshift.com/container-platform/4.11/cicd/pipelines/understanding-openshift-pipelines.html
  - Upstream project - Tekton: https://tekton.dev/docs/
- OpenShift Service Mesh: https://docs.openshift.com/container-platform/4.11/service_mesh/v2x/ossm-about.html
  - Upstream project - Istio: https://istio.io/latest/docs/
- Helm Package Management: https://helm.sh/docs/
- Deploy Azure Bicep files using GitHub Actions: https://learn.microsoft.com/azure/azure-resource-manager/bicep/deploy-github-actions
- Azure Red Hat OpenShift documentation: https://learn.microsoft.com/azure/openshift/
- Tutorial: Create an Azure Red Hat OpenShift cluster: https://learn.microsoft.com/azure/openshift/tutorial-create-cluster

If you enjoyed the episode and want more content like it? Try our monthly developer newsletter: https://aka.ms/DevNewsletterJoin

***

## 2022-09-15: Event driven architectures and the power of asynchronous communications

If you missed the live show you can catch the episode on [YouTube](https://youtu.be/VHUcv35Qxr0). The live segment Q&A is not included in this video, so if you'd like to see what was asked, along with answers, check out the [episode Q&A page](qanda/S02E11LiveQandA.md).

As the services and apps we build become increasingly distributed, integrations between components become increasingly complicated, error prone and difficult to manage.

In this episode of New Breakpoint, [Amit Kuckreja](https://www.linkedin.com/in/amitkuckreja/) from Microsoft will talk through how to solve these challenges using event-driven architectures and asynchronous communication. We'll also explore the right time to use them, the trade-offs that you make and some of the pain points.

Want to learn more? Here are some great next steps:

- What do you mean by "Event-Driven"? https://martinfowler.com/articles/201701-event-driven.html
- The Many Meanings of Event-Driven Architecture (video): https://youtu.be/STKCRSUsyP0 
- Event-Driven Architecture: A Primer: https://highalpha.com/event-driven-architecture-a-primer/
- Event-drive architecture style: https://docs.microsoft.com/azure/architecture/guide/architecture-styles/event-driven 
- Events, Data Points, and Messages - Choosing the right Azure messaging service for your data: https://azure.microsoft.com/en-us/blog/events-data-points-and-messages-choosing-the-right-azure-messaging-service-for-your-data/
- Architecture patterns for event-driven applications using Azure Functions (video): https://youtu.be/3hitbh6aCJc

If you enjoyed the episode and want more content like it? Try our monthly developer newsletter: https://aka.ms/DevNewsletterJoin

***

## 2022-06-09: Stop worrying about Kubernetes with Azure Container Apps and Dapr

If you missed the live show you can catch the episode on [YouTube](https://youtu.be/vUVTnfXEYW8). The live segment Q&A is not included in this video, so if you'd like to see what was asked, along with answers, check out the [episode Q&A page](qanda/S02E10LiveQandA.md).

Friend of New Breakpoint, [Todd Whitehead](http://twitter.com/todwhitehead) is back, and this time he's covering Azure Container Apps and showing us how the service eases developer's lives when building cloud-native microservices solutions. You can build multi-language microservices and utilise Dapr to manage integration, along with having scale-to-zero capabilities driven by the use of KEDA.

Want to learn more? Here are some great next steps:

- Container Apps overview: https://aka.ms/containerapps 
- Container Apps quickstart: https://docs.microsoft.com/azure/container-apps/get-started
- Learn more about Dapr: https://docs.dapr.io/
- Learn more about KEDA: https://keda.sh/

If you enjoyed the episode and want more content like it? Try our monthly developer newsletter: https://aka.ms/DevNewsletterJoin

***

## 2022-05-12 - Series 2 - Episode 9: Practical design steps architects can take to cost optimise their tech stack

If you missed the live show you can catch the episode on [YouTube](https://youtu.be/kW-pbYw_1QE).

Microsoft Australia's Chief Azure Architect, [Shane Baldacchino](https://www.linkedin.com/in/shanebaldacchino/) look at how you can manage costs by selecting Azure services based not only on their service capabilities, but also their cost profile. Nobody ever said they wanted to spend more money in the cloud!

Want to learn more? Here are some great next steps:

- Sample application we started with: https://github.com/sjwaight/PythonAussieDunnyDataAPI
- Sample application running on Azure Functions: https://github.com/sjwaight/ServerlessDownunderDunnies
- Microsoft Azure Well-Architected Framework (WAF) Cost Optimisation:
    - Overview: https://docs.microsoft.com/azure/architecture/framework/cost/overview
    - Design: Develop a cost model: https://docs.microsoft.com/azure/architecture/framework/cost/design-model
    - Monitor: Set budgets and alerts: https://docs.microsoft.com/azure/architecture/framework/cost/monitor-alert
    - Optimise: Checklist - optimise cost: https://docs.microsoft.com/azure/architecture/framework/cost/optimize-checklist

If you enjoyed the episode and want more content like it? Try our monthly developer newsletter: https://aka.ms/DevNewsletterJoin

***

## 2022-04-14 - Series 2 - Episode 8: Improve your application resilience with Azure Chaos Studio

If you missed the live show you can catch the episode on [YouTube](https://youtu.be/eEdGa3tjRDs).

In this episode of New Breakpoint, we are joined by Microsoft Azure Digital & App Innovation Specialist [Martin Abbott](https://twitter.com/martinabbott) to demonstrate how Azure Chaos Studio can help you test for potential points of failure at any phase of the service lifecycle – from development through to production.

Want to learn more? Here are some great next steps:

- The Principles of Chaos Engineering: https://principlesofchaos.org/
- How to run and manage an experiment with Chaos Studio: https://docs.microsoft.com/azure/chaos-studio/chaos-studio-run-experiment
- How to schedule an experiment: https://docs.microsoft.com/en-us/azure/chaos-studio/tutorial-schedule
- Sample application used for the session demo: https://github.com/ScottHolden/LiveInstanceDemo

If you enjoyed the episode and want more content like it? Try our monthly developer newsletter: https://aka.ms/DevNewsletterJoin

***

## 2022-03-10 - Series 2 - Episode 7: Let's brew Java on Azure 

If you missed the live show you can catch the episode on [YouTube](https://youtu.be/dEQoJza27ug).

Azure provides you with best-in-class solutions to build, test and deploy Java apps. With its managed services, Azure enables you to ship software faster — without worrying about infrastructure. Plus, you can take advantage of the extensibility of the Azure ecosystem to innovate and meet customer demands.

Microsoft's [Manoj Ravikumar Nair](https://www.linkedin.com/in/powershellpro/) walked us through how you can migrate and scale Java apps on Azure using all your favourite tools and frameworks, such as Spring, Tomcat, WildFly, JBoss, WebLogic, WebSphere, Maven, Gradle, IntelliJ, Eclipse, Jenkins, Terraform and more.

Want to learn more? Here are some great next steps:

- Azure for Java developers documentation: https://docs.microsoft.com/azure/developer/java/
- Microsoft Learn - Java on Azure Learning Path: https://docs.microsoft.com/learn/paths/get-started-java-azure/
- Quickstart: Deploy your first app to Azure Spring Cloud: https://docs.microsoft.com/azure/spring-cloud/quickstart?tabs=Azure-CLI&pivots=programming-language-java
- Migrate Tomcat applications to Tomcat on Azure App Service: https://docs.microsoft.com/azure/developer/java/migration/migrate-tomcat-to-tomcat-app-service
- Deploy a Spring app to App Service with MySQL: https://docs.microsoft.com/azure/developer/java/spring-framework/spring-app-service-e2e?tabs=bash
- Deploy a Payara Micro Web App to Azure App Service with Maven: https://docs.microsoft.com/azure/developer/java/eclipse-microprofile/deploy-microprofile-payara-micro-java-app-with-maven-plugin
- Azure Spring Cloud disaster recovery: https://docs.microsoft.com/azure/spring-cloud/disaster-recovery
- Deploying Azure Spring Cloud with VNet integration: https://docs.microsoft.com/azure/spring-cloud/how-to-deploy-in-azure-virtual-network?tabs=azure-portal
- Attend Microsoft's Java Developer conference 2022: https://aka.ms/JDConf-2022/

If you enjoyed the episode and want more content like it? Try our monthly developer newsletter: https://aka.ms/DevNewsletterJoin

***

## 2022-02-02 - Series 2 - Episode 6: Next-level Infrastructure-as-Code with Bicep and DevOps 

If you missed the live show you can catch the episode on [YouTube](https://youtu.be/K0BNRQQKvww). The live segment Q&A is not included in this video, so if you'd like to see what was asked, along with answers, check out the [episode Q&A page](S02E06LiveQandA.md).

Bicep makes it easy to deploy your Azure resources as code. But deploying Bicep code automatically requires you to know about pipelines, service principals, source control, and many other concepts.

In this episode, [John Downs](https://twitter.com/jdwns), Senior FastTrack Engineer from Microsoft, will talk through how you can get started building your own Azure deployment pipeline with Bicep, Azure Pipelines or GitHub Actions.

Want to learn more? Here are some great next steps:

- Learn how to work with Bicep: https://aka.ms/learnbicep
- Bicep Playground: https://aka.ms/bicepdemo
- Quickstart: Create Bicep files with Visual Studio Code: https://docs.microsoft.com/azure/azure-resource-manager/bicep/quickstart-create-bicep-use-visual-studio-code?tabs=CLI
- Quickstart: Integrate Bicep with Azure Pipelines: https://docs.microsoft.com/azure/azure-resource-manager/bicep/add-template-to-azure-pipelines?tabs=CLI
- Quickstart: Deploy Bicep files by using GitHub Actions: https://docs.microsoft.comazure/azure-resource-manager/bicep/deploy-github-actions?tabs=CLI

If you enjoyed the episode and want more content like it? Try our monthly developer newsletter: https://aka.ms/DevNewsletterJoin

***

## 2021-12-07 - Series 2 - Episode 5: Demystifying OAuth, JWTs and Azure AD for Developers

If you missed the live show you can catch the episode on [YouTube](https://youtu.be/mf7StZ62_R0). The live segment Q&A is not included in this video, so if you'd like to see what was asked, along with answers, check out the [episode Q&A page](qanda/S02E05LiveQandA.md).

Building applications to make use of Azure Active Directory (Azure AD) for authentication and authorisation requires developers to have familiarity with OAuth, Open ID Connect (OIDC) and JSON Web Tokens (JWTs). In this episode, [Graeme Foster](https://twitter.com/graefoster), Cloud Solution Architect from Microsoft, will use a fun interactive demonstration to familiarise developers with OAuth flows, Application Registrations and how to work with JWTs. 

In the episode you'll learn about what's inside ID and Access tokens, what Scopes and Roles are and how to use them, and, intriguingly... why there’s a Pixie (PKCE) lurking in your Azure AD flows!

Want to learn more? Here are some great next steps:

- Microsoft identity platform and OAuth 2.0 authorization code flow: https://docs.microsoft.com/azure/active-directory/develop/v2-oauth2-auth-code-flow
- Migrate applications to the Microsoft Authentication Library (MSAL): https://docs.microsoft.com/azure/active-directory/develop/msal-migration
- Add app roles to your application and receive them in the token: https://docs.microsoft.com/azure/active-directory/develop/howto-add-app-roles-in-azure-ad-apps
- Summary of the main differences between Azure AD Endpoint v1 and v2, with a focus on client libraries and supportability: https://nicolgit.github.io/AzureAD-Endopoint-V1-vs-V2-comparison/
- Interesting blog post 'The State of the Implicit Flow in OAuth2': https://brockallen.com/2019/01/03/the-state-of-the-implicit-flow-in-oauth2/
- Graeme's fun "SantaWeb" demo application from the talk - https://github.com/graemefoster/WhatsInTheToken

If you enjoyed the episode and want more content like it? Try our monthly developer newsletter: https://aka.ms/DevNewsletterJoin

***

## 2021-11-18 - Series 2 - Episode 4: Azure Application Services on Kubernetes with Azure Arc

If you missed the live show you can catch the episode on [YouTube](https://youtu.be/2mUpbTPUBh0). The live segment Q&A is not included in this video, so if you'd like to see what was asked, along with answers, check out the [episode Q&A page](qanda/S02E04LiveQandA.md).

In this show, Microsoft's [Chris Reddington](https://www.linkedin.com/in/chrisreddington/) walked us through how to run Azure App Service, Functions, Logic Apps and more on an Azure Arc-enable Kubernetes cluster and these clusters can be run on-premises or hosted in a third-party cloud. We saw how this approach allows you to take advantage of App Service features while also maintaining corporate compliance by hosting apps on infrastructure you manage. This also allows you to buy applications to take advantage of Azure Application Services and run them in Azure and elsewhere which is great for business continuity or disaster recovery.

Want to learn more? Here are some great next steps:

- Microsoft Learn module on implementing Azure App Service on Kubernetes with Arc - https://docs.microsoft.com/learn/modules/configure-application-kubernetes-arc/
- Overview of App Service, Functions and Logic Apps on Azure Arc - https://docs.microsoft.com/azure/app-service/overview-arc-integration
- Learn more about Event Grid on Kubernetes with Azure Arc - https://docs.microsoft.com/azure/event-grid/kubernetes/overview
- API Management Gateway on Azure Arc - https://docs.microsoft.com/azure/api-management/how-to-deploy-self-hosted-gateway-azure-arc

If you enjoyed the episode and want more content like it? Try our monthly developer newsletter: https://aka.ms/DevNewsletterJoin

***

## 2021-10-07 - Series 2 - Episode 3: BRUVNet & Azure AI: Unravelling the Data in our fish community

If you missed the live show you can catch the episode on [YouTube](https://youtu.be/nnHmVKsERNw). All the questions raised during the live Q&A are already answered either in the video or in the list below.

Azure custom vision with machine learning is a great way to train and visualise data sets, operationalise machine learning models to save hundreds of hours of manual work and enable citizen scientists and power collaboration. In this episode, host [Michelle Sandford](https://www.linkedin.com/in/michellesandford/) is joined by [Rupal Mudholkar](https://www.linkedin.com/in/rupal-thakkar-mudholkar/) from the Microsoft FastTrack Team, as well as [Andrew Jansen](https://www.linkedin.com/in/andrew-jansen-ecologist/) and [Keith Tayler](https://www.linkedin.com/in/keith-tayler-a4535284/) from the Australian Government's Supervising Scientist Branch (SSB) Project in Kakadu to learn how the team is using data, Azure AI and Machine Learning to extend the project's capabilities, supporting scientists and researchers who are making a difference. 

Want to learn more? Here are some great next steps:

- BRUVNet Open Source Scripts: https://github.com/ajansenn/BRUVNet
- Global Biodiversity Information Facility: https://www.gbif.org/ 
- Image Labelling Challenge on BRUVnet: https://www.bruvnet.org/
- Supervising Scientist on Facebook: https://www.facebook.com/SSBgov/
- Azure Custom Vision: https://docs.microsoft.com/azure/cognitive-services/custom-vision-service/
- Learn how to use Azure Custom Vision  https://docs.microsoft.com/learn/browse/?terms=%22Custom%20Vision%22
- Azure Machine Learning documentation: https://docs.microsoft.com/azure/machine-learning/overview-what-is-azure-machine-learning
- FastTrack for Azure (FTA for short): https://azure.microsoft.com/programs/azure-fasttrack/
- AI for Earth: https://www.microsoft.com/ai/ai-for-earth-tech-resources
- Citizen scientists, AI and cloud monitor Kakadu billabongs, support Ranger uranium mine rehabilitation https://news.microsoft.com/en-au/features/citizen-scientists-ai-and-cloud-monitor-kakadu-billabongs-support-ranger-uranium-mine-rehabilitation/

If you enjoyed the episode and want more content like it? Try our monthly developer newsletter: https://aka.ms/DevNewsletterJoin

***

## 2021-09-09 - Series 2 - Episode 2: Migrating PHP Laravel web apps to Azure App Service

If you missed the live show you can catch the episode [on YouTube](https://youtu.be/fdaZmUHCamI). All the questions raised during the live Q&A are already answered either in the video or in the list below.

Azure App Service is a great place to host your web applications, and one of the most common web frameworks, PHP, is deeply supported on the platform. This episode we are joined by Microsoft's [Rajan Bhayana](https://www.linkedin.com/in/rajan-bhayana-3933b547/) to talk through App Service's PHP support and how you migrate your existing Laravel applications to Azure. 

Want to learn more? Here are some great next steps:

- Configure a PHP app for Azure App Service: https://docs.microsoft.com/azure/app-service/configure-language-php?pivots=platform-linux
- App Service Migration Assistant (which supports PHP migration): https://azure.microsoft.com/services/app-service/migration-assistant/
- Azure Database for MySQL: https://docs.microsoft.com/azure/mysql/
- GitHub Actions for PHP: https://github.com/marketplace?type=actions&query=PHP
- Demo application used during show: https://github.com/parthp1808/Laravel-todo-app
- App Service's in-built CI/CD (Kudu) documentation: https://github.com/projectkudu/kudu/wiki

If you enjoyed the episode and want more content like it? Try our monthly developer newsletter: https://aka.ms/DevNewsletterJoin

***

## 2021-08-12 - Series 2 - Episode 1: Modernising your CI/CD pipelines

If you missed the live show you can catch the episode [on YouTube](https://youtu.be/OtQh-8mcc4g). The live segment Q&A is not included in this video, so if you'd like to see what was asked, along with answers, check out the [episode Q&A page](qanda/S02E01LiveQandA.md).

[Anthony Borton](https://twitter.com/AnthonyBorton) from GitHub walked us through GitHub Actions triggered from a Pull Request (PR) and how Actions can be used to drive easier PR validation. We also saw how to add sophisticated security scanning that looks for both secrets and code vulnerabilities to our deployments to Azure (or any destination!)

Want to learn more? Here are some great next steps:

- GitHub Actions Quickstart: https://docs.github.com/en/actions/quickstart
- GitHub Actions Reference: https://docs.github.com/en/actions/reference
- Explore the community of GitHub Actions in the marketplace: https://github.com/marketplace?type=actions
- Learn more about GitHub Copilot (currently in technology preview): https://copilot.github.com/
- GitHub Codespaces is now Generally Available as this episode goes to air: https://docs.github.com/en/codespaces/overview

If you enjoyed the episode and want more content like it? Try our monthly developer newsletter: https://aka.ms/DevNewsletterJoin

***

## Check out Series 1

We had some great talks covering a range of developer and AI topics, including DevOps, MLOps, Python and Serverless.

All Series 1 shows are listed on our [Series 1 page](series-01.md).
