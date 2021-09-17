## Usage

[Helm](https://helm.sh) must be installed to use the charts.  Please refer to
Helm's [documentation](https://helm.sh/docs) to get started.

Once Helm has been set up correctly, add the repo as follows:

  helm repo add helm-selenium https://frste.github.io/helm-charts

If you had already added this repo earlier, run `helm repo update` to retrieve
the latest versions of the packages.  You can then run `helm search repo
helm-selenium` to see the charts.

To install the selenium-grid chart:

    helm install my-selenium-grid helm-selenium/selenium-grid

To uninstall the chart:

    helm delete my-selenium-grid
