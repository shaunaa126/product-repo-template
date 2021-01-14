# backlog-automation
A POC for automating (triaging) various issues in a single backlog project [Org-Backlog](https://github.com/orgs/TnT-Test/projects/7). The Org-Backlog project is configured with the following columns: `Review`, `Backlog`, `In Progress`, and `Done`.

## How to get started - the Work Item Management process
Proposed workflow: Create Issue --> Review --> Approve --> Backlog --> Assign --> In Progress --> Completed/Done
1. Create an issue in this repository, three issue types are available `bugs`, `user story`, `feature`. 
2. Fill out the details in the issue and submit. By providing **Product name** somewhere in the issue, the work item will automatically be assigned to the product's corresponding "Product Owner or Tech Lead" for `Review` and will be added to the `Review` column in the [Org-Backlog](https://github.com/orgs/TnT-Test/projects/7).
3. Once the issue has been manually reviewed by the required parties, apply the `approved` label and remove the `needs review` label when the item is ready to be worked on. The work item will automatically transition to the `Backlog` column where it is ready to be picked up and assigned. In addition, manually apply a milestone to the work item to track its progress.
4. Assign the issue to an engineer in the Squad when the item is ready to be worked on. The work item will automatically transition to the `In Progress` column.
5. Apply the `completed` label or **close** the issue when the work has been completed. The work item will automatically transiton to the `Done` column.

## Templates and GitHub Actions used for the automation
* Utilizes Github [Issue Templates](https://docs.github.com/en/free-pro-team@latest/github/building-a-strong-community/configuring-issue-templates-for-your-repository) under `.github/ISSUE_TEMPLATE/*template.md` to define issue types `bugs`, `user story`, `feature`. 
* https://github.com/crazy-max/ghaction-github-labeler --> Manage labels as code. The following labels are available to be used in the project: `needs review`, `approved`, `completed`, `ProductA`, `ProductB`, `Squad1`, `Squad2`, `Points: 2`, `Points: 4`, etc.
* The following milestones are available to be used in the project: `Release: 2021-REL-01`, `Release: 2021-REL-02`, `Release: 2021-REL-03`, `Release: 2021-REL-04`.
* https://github.com/damccorm/tag-ur-it --> Automatically tag issues with labels and assignees based on issue rules. Use this to look for Product name in the issue and assign to Product Owners/Tech Leads.
* https://github.com/peaceiris/actions-label-commenter --> Post comment to issue based on label rules.
* https://github.com/alex-page/github-project-automation-plus --> Use issue webhooks to transition issues (project cards) to their respective columns.