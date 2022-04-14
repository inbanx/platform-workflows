# Platform workflows
Github actions and workflows for platform experiences. We want a centralized reusable workflow library to streamline our github actions.

## Usage
In order to implement a workflow in your repository you will need to add the job to your definition `yml` file:
```yaml
jobs:
  job-name:
    uses: inbanx/platform-workflows/workflows/<WORKFLOW_NAME>.yml@<BRANCH>
```

## Contribution
Inside of `workflows` folder add the new workflow you want to contribute. To be able to consume the workflow you need to define it under
the `workflow_call` definition. You will need to define its inputs and secrets that it requires to execute.

```yaml
on:
  workflow_call:
    inputs:
      input_name:
        default: "example"
        required: false
        description: "Example field"
        type: string
        ...
    secrets:
      example:
        required: true
        ...
```
You can read more about setting up workflows [here](https://docs.github.com/en/actions/using-workflows/reusing-workflows#creating-a-reusable-workflow)
