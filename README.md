# action-fetch-helm-chart

GitHub action to fetch Helm chart from ECR using OCI and explode locally.

> **NOTE**: This action uses a workaround for v3.7.0 see [github issue](https://github.com/helm/helm/issues/10122#issuecomment-922900257)

## Usage

```yaml
    - uses: aws-actions/configure-aws-credentials@v1
      with:
        aws-access-key-id: ${{ secrets.ECR_AWS_ACCESS_KEY_ID }}
        aws-secret-access-key: ${{ secrets.ECR_AWS_SECRET_ACCESS_KEY }}
        aws-region: ap-southeast-1
    - uses: hyphengroup/action-fetch-helm-chart@v0.1.2
      with:
        chart: hyphen-service
        version: 0.1.0
        registryUrl: ${{ secrets.ECR_REGISTRY_URL }}
```

Example logs:

```
Login Succeeded
Pulled: ***/charts/hyphen-service:0.1.0
Digest: sha256:6f3cd7baf83a9d3771df37bc27103c2fbcdaa6b026499d954fd754b6d5c47961
hyphen-service/Chart.yaml
hyphen-service/values.yaml
...
```
