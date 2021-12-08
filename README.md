# repo-name

Suggested use:

```yaml
jobs:
  list:
    name: List service accounts
    runs-on: ubuntu-latest
    # GitHub token needs oidc permissions (id-token), which it doesn't get by default
    # Ensure that any other permissions your job needs are also included below
    permissions:
      contents: read
      id-token: write
    steps:
      - name: gcloud setup with workload identity
        uses: vivantehealth/gcloud-workload-identity-action@v1
      - name: List accounts
        run: gcloud iam service-accounts list
```
