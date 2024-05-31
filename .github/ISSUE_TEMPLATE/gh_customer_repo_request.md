name: '🗓️ GitHub Customer Repo Request'
description: Request a customer repo inside githubcustomers organization
title: '[Customer Repository]: {CUSTOMER}'
labels:
  - 'Project'
  - 'Customer Repo'
assignees: []
body:
  - type: markdown
    attributes:
      value: |
        A single issue should be associated with a single customer repo - if you want to provision multiple customer repos, please open multiple issues.

        If customer repo already exists under a different name, issue comments will contain the existing repo URL.

        Provisioning of customer GitHub project (Kanban or Backlog style) is optional, but recommneded. 
        
  - type: input
    id: account_name
    attributes:
      label: Customer
    validations:
      required: true

  - type: input
    id: githubcustomers_repo_url
    attributes:
      label: Customer repository
      placeholder: https://github.com/githubcustomers/...
    validations:
      required: true

  - type: dropdown
    id: need_github_project
    attributes:
      label: Need Github Project
      options:
        - No GitHub Project Required
        - Kanban-style
        - Backlog-style 
    validations:
      required: true

  - type: markdown
    attributes:
      value: |
        # Custom instructions

        _Provide any additional information helpful for repo provisioning and content_

  - type: textarea
    id: repo_admins_users
    attributes:
      label: Repository Admin User Handles
      placeholder: Please provide a comma-separated list of GitHub user handes who require repo admin access (e.g. @user1, @user2 ...).

  - type: markdown
    attributes:
      value: |
        <sup>**Please note:** this issue was created from [this issue template][template-issue]. PRs to update @mentioned teams, individuals, checklists items, etc. welcome.</sup>

        <!-- Links -->

        [template-issue]: https://github.com/github/services/tree/HEAD/.github/ISSUE_TEMPLATE/Operations.Scheduling_Request.yml
