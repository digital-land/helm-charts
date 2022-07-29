# digital-land/helm-charts
A helm chart repository for managing the applications in the digital land ecosystem.

## Usage

Add the helm repository.

`helm repo add digital-land https://digital-land.github.io/helm-charts`

Install a chart.

`helm install digital-land-platform digital-land/web-application`

Preview a helm chart.

`helm template -f examples/digital-land-platform/values.yaml digital-land-platform digital-land/web-application`
