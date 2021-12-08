# repo-name

Suggested use:

```yaml
jobs:
  list:
    name: List service accounts
    runs-on: ubuntu-latest
    steps:
      - name: gcloud setup with workload identity
        uses: vivantehealth/gcloud-workload-identity-action@v1
      - name: List accounts
        run: gcloud iam service-accounts list
```
