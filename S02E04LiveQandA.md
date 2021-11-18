## 2021-11-18 - Series 2 - Episode 4: Azure Application Services on Kubernetes with Azure Arc - Q&A

During the live session we did a live Q&A spot where attendees could ask questions. If you didn't manage to make it along, here are the ones that came up, along with the answer where possible.

### ❔ What are the main business use cases that you see clients use this for?

A combination of business continuity and disaster recovery, along with compliance and governance. This service allows developers to build with Azure App Service knowing that it can run in multiple locations (including Azure), but that it can be managed consistently regardless of hosting location.

### ❔ Will the Azure components in Arc have the same HA, SLA and scaling rules as the native components outside of Arc? E.g. App Service in ARC On Prem vs App Service Azure Native.

Generally speaking, the availability and associated SLA for any non-Azure service is the responsibility of the party who provides the hosting platform. This may be another cloud provider, a third-party hosting provider, or your in-house infrastructure team. Microsoft will be responsible for the SLA for the management plane inside of Azure that is used to manage the remote Azure Arc cluster.

### ❔ Are there any rough dates when App Service for Arc K8s will be ready for production usage? Same question for Event Grid preview? When will preview or production be available in Australia regions?

Currently no public dates for General Availability (Production usage). Expansion of the preview to additional Regions beyond US East and Western Europe isn't currently planned, but may occur depending on demand.

### ❔ How does this setup handle Internet connection disruption? 2- What are the identity requirements? Can the on-prem K8S use an identity/authorization source other than Azure AD. E.g. on-Prem Active Directory

Azure Arc supports disconnected Kubernetes clusters in certain configurations, though there are impacts on management activities for long periods of disconnection due to Azure Arc Agent [certificate expiration](https://docs.microsoft.com/azure/azure-arc/kubernetes/faq#how-to-address-expired-azure-arc-enabled-kubernetes-resources). The various Extensions deployed via Azure Arc (Azure Application Services is one of these) have different requirements around internet connectivity with some features such as CI/CD into App Services not functioning as expected when your Kubernetes environment is disconnected from Azure.

For identity, if you choose to use [Azure RBAC](https://docs.microsoft.com/azure/azure-arc/kubernetes/conceptual-azure-rbac) to secure your Arc-Enabled Kubernetes cluster then you will take a dependency on Azure Active Directory for cluster security. Outside of this, just the previously mentioned Azure Arc Agent is required for Azure Arc to manage your cluster. On-premises Active Directory is not supported.

### ❔ Do app services slots get a separate container per instance.

Slots run as separate Pods on the Cluster.

### ❔ If we're calculating SLA for items such as Logic App Standard and APIM, is it possible to calculate SLA for the ARC enabled resources?

Please see the earlier question on HA and SLAs.