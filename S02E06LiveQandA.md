## 2022-02-02 - Series 2 - Episode 6: Next-level Infrastructure-as-Code with Bicep and DevOps - Q&A

During the live session we did a live Q&A spot where attendees could ask questions. If you didn't manage to make it along, here are the ones that came up. We've included answers where possible.

### ❔ Does the Azure Pipelines build pipeline work with the release pipelines features (approvals, etc) - are there two separate pipelines (build and release) or is it merges all into one?

We were working with YAML pipelines, which don't distinguish between builds and releases – it's one big pipeline that might have different stages for building and deploying your code. Check out this [Learn module for more information](https://docs.microsoft.com/learn/modules/test-bicep-code-using-azure-pipelines/). 

### ❔Is it possible to break a main bicep file into separate files?

Yes, it is – you can use an awesome feature called modules to do this. Here's [more information](https://docs.microsoft.com/learn/modules/create-composable-bicep-files-using-modules/) 

### ❔Should you, or is it possible to, deploy multiple services to multiple environments in one pipeline?

This is a tricky one to give an answer to because it depends on the situation. Deploying to multiple environments in the same pipeline is a good idea (see [here for more info](https://docs.microsoft.com/learn/modules/manage-multiple-environments-using-bicep-azure-pipelines/) and [here](https://docs.microsoft.com/learn/modules/manage-multiple-environments-using-bicep-github-actions/)). Generally, it's best to have a single pipeline deploy one 'service' and not multiple services – but it depends on your scenario and how your organisation works.

### ❔ Could you share some recommendations / tips on retrieving Shared Access Keys and using it downstream in a pipeline using Bicep?

Usually it's a good idea to look up secrets, like shared access keys, right before you need to use them rather than passing them around – because it's easy to accidentally handle them insecurely when you pass them around. Here's our documentation around [handling secrets and templates](https://docs.microsoft.com/azure/azure-resource-manager/bicep/scenarios-secrets#look-up-secrets-dynamically). You should also try to use managed identities instead of keys wherever you can, which eliminates the need for passing keys around at all – check out our Bicep [guidance on secrets and identities](https://docs.microsoft.com/azure/azure-resource-manager/bicep/scenarios-secrets#avoid-secrets-where-you-can). 

If you're looking at how to write to a storage account or database from within your pipeline, check out these Learn modules which include useful information on [Azure Pipelines](https://docs.microsoft.com/learn/modules/manage-end-end-deployment-scenarios-using-bicep-azure-pipelines/) and [GitHub Actions](https://docs.microsoft.com/learn/modules/manage-end-end-deployment-scenarios-using-bicep-github-actions/). 

### ❔ Is it possible to deploy bicep templates from multiple repositories? For example, the bicep code for creating a function app can be reused and be kept in a generic repository. And the app settings that is specific to a project could be kept in its own repo.

You can do that, yes. Here's how you do it in [Azure Pipelines](https://docs.microsoft.com/azure/devops/pipelines/repos/multi-repo-checkout?view=azure-devops) and in [GitHub Actions](https://github.com/actions/checkout/issues/24).

It is also worth looking at [Bicep module registries](https://docs.microsoft.com/azure/azure-resource-manager/bicep/private-module-registry), which are a better way to do what you are trying achieve. 