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

### Bug Table

| Bug | Cause | Fix |
|---|---|---|
| Composite action output is not available | The output was not connected to the correct step output | Set `id: create-greeting` on the greeting step and use `${{ steps.create-greeting.outputs.greeting }}` |
| Greeting output is empty | The value was not written to `$GITHUB_OUTPUT` | Use `echo "greeting=$greeting" >> "$GITHUB_OUTPUT"` |
| Greeting step output cannot be accessed from the reusable workflow | `id: greet` was assigned to the checkout step instead of the composite action step | Move `id: greet` to the step that uses `./.github/actions/greet` |


## Q4

### Successful Workflow Run

https://github.com/sahilshirsath96k/gha-assignment/actions/runs/34367655124/job/102520441682

### Bug Table

### Bug Table

| Bug | Cause | Fix |
|---|---|---|
| Job is skipped when `staging` is selected | The job has `if: ${{ inputs.environment == 'production' }}` at job level | Remove the job-level `if` so the job runs for both environments |
| Environment input accepts arbitrary text | The `workflow_dispatch` input does not specify a choice type | Add `type: choice` and define `staging` and `production` under `options` |
| Production deployment does not run correctly | The production condition is applied to the entire job instead of only the deployment step | Move `if: ${{ inputs.environment == 'production' }}` to the simulated production deploy step |
| Guarded step condition is not explicitly evaluated | The condition does not explicitly use the expression syntax | Use `if: ${{ env.APP_NAME == 'demo-app' }}` |
| Notify step never runs | `success() && failure()` can never be true at the same time | Replace it with `if: ${{ always() }}` |


## Q5

### Successful Workflow Run

https://github.com/sahilshirsath96k/gha-assignment/actions/runs/34243110711/job/102118118869

### Bug Table

### Bug Table

| Bug | Cause | Fix |
|---|---|---|
| `consume` job cannot access the generated version | The dependency on the `generate` job is missing | Add `needs: generate` to the `consume` job |
| `steps.make.outputs.version` is unavailable | The `Make version` step does not have `id: make` | Add `id: make` to the `Make version` step |
| Version output is not generated correctly | The deprecated `::set-output` command is being used | Write the output using `echo "version=1.0.$GITHUB_RUN_NUMBER" >> "$GITHUB_OUTPUT"` |
| Workflow may fail to parse or behave incorrectly | YAML indentation is incorrect | Correct the indentation of `jobs`, `steps`, `outputs`, and other nested properties |
