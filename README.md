# DevCycle Secrets Manager

This GitHub Action sets GitHub Secrets securely from AWS Secrets Manager.

## Inputs

- **`secrets_map`**: A JSON object of environment variables mapped to AWS Secrets Manager secret names. (required)
- **`role_prefix`**: The prefix of the role to assume in the target AWS account. Default: `GitHub-Actions-`. (required)
- **`aws_region`**: The AWS region where the secrets are stored. Default: `us-east-1`. (required)
- **`aws_account_id`**: The AWS account ID where the secrets are stored. . (required)

## Usage

```yaml
name: Example Workflow
on: [push]

jobs:
  example-job:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v2

      - name: Set Secrets
        uses: ./
        with:
          secrets_map: '{"MY_SECRET": "my-aws-secret-name"}'
          role_prefix: 'GitHub-Actions-'
          aws_region: 'us-east-1'
          aws_account_id: ''
```
