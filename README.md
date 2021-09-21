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

Example logs:

```
Login succeeded
0.1.0: Pulling from ***/charts/hyphen-service
ref:     ***/charts/hyphen-service:0.1.0
digest:  96184f4838f0676a214813aecd816a91cd87a097a3bf240888689f984574d9d0
size:    2.6 KiB
name:    hyphen-service
version: 0.1.0
Status: Downloaded newer chart for ***/charts/hyphen-service:0.1.0
ref:     ***/charts/hyphen-service:0.1.0
digest:  96184f4838f0676a214813aecd816a91cd87a097a3bf240888689f984574d9d0
size:    2.6 KiB
name:    hyphen-service
version: 0.1.0
Exported chart to .helm/charts/hyphen-service/
```
