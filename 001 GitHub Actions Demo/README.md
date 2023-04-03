# GitHub Actions Demo

## Script 

``` yml
name: GitHub Actions Demo
run-name: ${{ github.actor }} is testing out GitHub Actions 🚀
on: [push]
jobs:
  Explore-GitHub-Actions:
    runs-on: ubuntu-latest
    steps:
      - run: echo "🎉 The job was automatically triggered by a ${{ github.event_name }} event."
      - run: echo "🐧 This job is now running on a ${{ runner.os }} server hosted by GitHub!"
      - run: echo "🔎 The name of your branch is ${{ github.ref }} and your repository is ${{ github.repository }}."
      - name: Check out repository code
        uses: actions/checkout@v3
      - run: echo "💡 The ${{ github.repository }} repository has been cloned to the runner."
      - run: echo "🖥️ The workflow is now ready to test your code on the runner."
      - name: List files in the repository
        run: |
          ls ${{ github.workspace }}
      - run: echo "🍏 This job's status is ${{ job.status }}."
```

## Output

```
✅ Setup job
✅ Run echo "🎉 The job was automatically triggered by a push event."
✅ Run echo "🐧 This job is now running on a Linux server hosted by GitHub!"
✅ Run echo "🔎 The name of your branch is refs/heads/main and your repository is tushar-prox/github-actions-test."
✅ Check out repository code
✅ Run echo "💡 The tushar-prox/github-actions-test repository has been cloned to the runner."
✅ Run echo "🖥️ The workflow is now ready to test your code on the runner."
✅ List files in the repository
✅ Run echo "🍏 This job's status is success."
✅ Post Check out repository code
✅ Complete job
```

## Contexts

Contexts are a way to access information about workflow runs, variables, runner environments, jobs, and steps. Each context is an object that contains properties, which can be strings or other objects.


| Name | Resolves to |
|:---|:---|
| github.actor | User who is performing the current action |
| github.event_name | Name of the event which triggered the current workflow |
| runner.os | OS in which current workflow is running |
| github.ref | Name of the current branch |
| github.repository | Name of the current repository |
| github.workspace | Current Repo path on runner machine |
| job.status | Status of current Job |


[More about Contexts](https://docs.github.com/en/actions/learn-github-actions/contexts)
