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
| Greeting output was not coming | Output was not connected with the correct step | Added step id and mapped the output correctly |
| Greeting value was empty | Output was not written to GitHub output | Used `$GITHUB_OUTPUT` to save the greeting |
| Greeting output was not accessible | `id` was given to the wrong step | Moved `id: greet` to the greeting action step |


## Q4

### Successful Workflow Run

https://github.com/sahilshirsath96k/gha-assignment/actions/runs/34367655124/job/102520441682

### Bug Table

| Bug | Cause | Fix |
|---|---|---|
| Job was skipped for staging | Condition was added at job level for production only | Removed the job level condition |
| Environment allowed free text | Input type was not defined | Added choice input with staging and production |
| Production message was not working correctly | Condition was applied to the complete job | Added condition only to the production step |
| Guarded step was not working properly | Condition was not written correctly | Corrected the condition using `env.APP_NAME` |
| Notify step was not running | `success()` and `failure()` cannot be true together | Changed the condition to `always()` |


## Q5

### Successful Workflow Run

https://github.com/sahilshirsath96k/gha-assignment/actions/runs/34243110711/job/102118118869

### Bug Table

| Bug | Cause | Fix |
|---|---|---|
| Version was not available in consume job | Dependency on generate job was missing | Added `needs: generate` |
| Version output was empty | Make step did not have an id | Added `id: make` |
| `set-output` was not working | The command is deprecated | Used `$GITHUB_OUTPUT` instead |
| Workflow had indentation issues | YAML structure was not properly aligned | Corrected the YAML indentation |
