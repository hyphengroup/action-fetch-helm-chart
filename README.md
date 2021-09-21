# action-fetch-helm-chart

GitHub action to fetch Helm chart from ECR using OCI (Helm 3.6.x )

> **NOTE**: This action is **not compatible with Helm 3.7.x** which 
> adds support for `oci://` protocol and removes special `chart` 
> subcommands

## Usage

```yaml
    - uses: aws-actions/configure-aws-credentials@v1
      with:
        aws-access-key-id: ${{ secrets.ECR_AWS_ACCESS_KEY_ID }}
        aws-secret-access-key: ${{ secrets.ECR_AWS_SECRET_ACCESS_KEY }}
        aws-region: ap-southeast-1
    - uses: hyphengroup/action-fetch-helm-chart@v0.1.0
      with:
        chart: hyphen-service
        version: 0.1.0
        registryUrl: ${{ secrets.ECR_REGISTRY_URL }}
```
