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
        uses: vivantehealth/gcloud-workload-identity-action@v3
        with:
          workload_identity_provider: ${{ secrets.BASE64_WORKLOAD_IDENTITY_PROVIDER }}
          gcp_service_account: ${{ secrets.BASE64_GCP_SERVICE_ACCOUNT }}
      - name: List accounts
        run: gcloud iam service-accounts list
```
