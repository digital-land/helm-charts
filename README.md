# digital-land/helm-charts
A helm chart repository for managing the applications in the digital land ecosystem.

## Usage

Add the helm repository.

`helm repo add digital-land https://digital-land.github.io/helm-charts`

Install a chart.

`helm install digital-land-platform digital-land/web-application`

Preview a helm chart.

`helm template -f examples/digital-land-platform-local/values.yaml digital-land-platform digital-land/web-application`

## Testing Locally

* Install NGINX ingress chart.
```
helm upgrade --install ingress-nginx ingress-nginx \
  --repo https://kubernetes.github.io/ingress-nginx \
  --namespace ingress-nginx --create-namespace
```
* Add a hostname alias for local loopback.
```
echo '127.0.0.1 digital-land.test' | sudo tee -a /etc/hosts
```
* Install the web application chart with the local example values.
```
helm upgrade --install \
  -f examples/digital-land-platform-local/values.yaml \
  digital-land-platform ./charts/web-application
```