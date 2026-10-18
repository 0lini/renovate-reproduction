# fleet: helm.repo: oci://... gets no updates

## Current behavior

Renovate proposes an update for `helm-chart-oci/fleet.yaml`, which uses `helm.chart: oci://...`.
Renovate proposes no update for `helm-repo-oci/fleet.yaml`, which is identical except that it uses `helm.repo: oci://...`.
The `helm.repo` dependency is skipped with `skipReason: missing-depname`.

## Expected behavior

Both bundles get the same update via the `docker` datasource with package name `registry-1.docker.io/bitnamicharts/external-dns`.
Fleet has deprecated OCI URLs in `helm.chart` and recommends `helm.repo` instead (see the [Fleet `fleet.yaml` reference](https://fleet.rancher.io/ref-fleet-yaml)).
For OCI, Fleet uses `helm.repo` as the complete chart reference and ignores `helm.chart`.

## Link to the Renovate issue or Discussion

https://github.com/renovatebot/renovate/discussions/47134
