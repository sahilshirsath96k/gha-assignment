# Solutions

## Q1

### Successful Workflow Run

https://github.com/sahilshirsath96k/gha-assignment/actions/runs/34224708673


## Q2

### Successful Workflow Run

https://github.com/sahilshirsath96k/gha-assignment/actions/runs/34372171900


## Q3

### Successful Workflow Run

https://github.com/sahilshirsath96k/gha-assignment/actions/runs/34223242261/job/102051101183

### Bug Table

| Bug | Cause | Fix |
|---|---|---|
| Workflow trigger is not written correctly | `push` and `workflow_dispatch` are not properly structured under `on` | Correct the `on` section with proper YAML indentation |
| Runner is not available | `ubuntu-latest-large` is not available in the current setup | Use `ubuntu-latest` |
| Hello script may fail | Repository is not checked out before running the script | Move `actions/checkout` before the script step |
| Checkout action is incomplete | `actions/checkout` is used without a version | Use `actions/checkout@v4` |


## Q4

### Successful Workflow Run

https://github.com/sahilshirsath96k/gha-assignment/actions/runs/34367655124/job/102520441682

### Bug Table

| Bug | Cause | Fix |
|---|---|---|
| Production condition is not working | `production` is written without quotes | Use `'production'` |
| Job is skipped for staging | Condition is applied to the whole job | Remove the job-level condition so the job runs for both environments |
| Environment allows free text | Input type is not specified | Add `type: choice` with `staging` and `production` options |
| Guarded step condition is not working | `env` variable is not referenced correctly | Use `${{ env.APP_NAME == 'demo-app' }}` |
| Notify step never runs | `success()` and `failure()` cannot be true together | Use `if: ${{ always() }}` |


## Q5

### Successful Workflow Run

https://github.com/sahilshirsath96k/gha-assignment/actions/runs/34243110711/job/102118118869

### Bug Table

| Bug | Cause | Fix |
|---|---|---|
| Version output is not created | `id: make` is missing from the Make version step | Add `id: make` |
| `set-output` is deprecated | Old output syntax is being used | Use `$GITHUB_OUTPUT` |
| Consume job cannot get the version | `needs: generate` is missing | Add `needs: generate` |
| Version check cannot get the output | The generate job output depends on the missing step id | Add `id: make` and write the version to `$GITHUB_OUTPUT` |
