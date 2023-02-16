## 2021-08-12 - Series 2 - Episode 1: Modernising your CI/CD pipelines - Q&A

During the live session we did a live Q&A spot where attendees could ask questions. If you didn't manage to make it along, here are the ones that came up. We've included answers where possible.

### ❔ I'm new to GitHub Actions. Is there somewhere I can go to get started?

There are two places to head to:

- The GitHub Actions documentation Quickstart: https://docs.github.com/en/actions/quickstart 
- The Microsoft Learn learning path: https://docs.microsoft.com/learn/paths/automate-workflow-github-actions/

### ❔ GitHub Codespaces looks great. Is it available to all GitHub users?

At time of writing (August 2021), Codespaces is only available to GitHub Team and Enterprise Cloud plan users. This may change in future, so always check the [official documentation](https://docs.github.com/en/codespaces).

### ❔ Azure DevOps for CI/CD vs GitHub Actions - is DevOps being phased out in favour of GitHub Actions?

This is a great question. The bottom line is investing your time in either platform is OK. GitHub Actions is the main focus for new and innovative features, but Azure DevOps is not going away any time soon and continues to be maintained and supported by Microsoft for the forseeable future. Any plans to retire Azure DevOps would be flagged well in advance and ensure you investements in Azure DevOps can be managed as they migrate to GitHub.

### ❔ Are Codespaces free to use?

There is a limited free period at launch which means qualified organisations can use them free until September 10, 2021. After that a payment option must exist for continued use. There is currently no published information around any future offers that may include a free tier. The best place to check the current state of pricing is the [official documentation](https://docs.github.com/en/billing/managing-billing-for-github-codespaces/about-billing-for-codespaces).

### ❔ Can outputs in workflow steps be markdown formatted?

A workflow is simply an orchestration that can invoke external Actions or script snippets, so in theory you could probably achieve this outcome. The best place to start would be the [GitHub Actions Marketplace](https://github.com/marketplace?type=actions) to see is someone has built something that does what you need.

### ❔ What happens to the PR slot created as part of the pull request workflow? The one with "github.event.number" in it's name? Does it get destroyed?

That's a great question! The demo doesn't show what happens to the slot, but needless to say, what you want to happen to it determines the approach taken. You can either choose to delete the resources via automation in Azure or have a Step in the GitHub Action that deletes it on successful deployment. It's important to note that Azure App Services can host multiple slots, so it might be that you simply re-use the slot for each following deployment.

### ❔ What approval gates options and external system integration capabilities are there? (eg: ServiceNow for change management)

To use approvals with GitHub Actions you must first setup [Environments](https://docs.github.com/en/actions/reference/environments). Once you have one or more Environment you can define rules around [required reviews for deployments](https://docs.github.com/en/actions/managing-workflow-runs/reviewing-deployments). Capabilities continue to be added to this space, so it's worth checking the official documentation to see what is currently available.

As to external integrations - as an example [ServiceNow has built Actions](https://github.com/marketplace?type=actions&query=servicenow+) that can be used in your workflows that may meet your requirements. Ultimately, if there is an API that you can call to automate something, then it is entirely possible to either integrate it yourself, or use a pre-built integration such as the one ServiceNow has already built.