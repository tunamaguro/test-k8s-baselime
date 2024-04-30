# test-k8s-baselime
baselimeを試してみるリポジトリ


## Setup

1. Create cluster

```bash
$ kind create cluster --config cluster.yaml
```

2. Create configuration yaml
```bash
$ cp baselime-values.yaml baselime-values.secret.yaml 
```

```yaml
apiKey: "YOUR_API_KEY"
```

3. Add Baselime Chart

```bash
$ helm repo add baselime-logs-exporter https://baselime.github.io/helm-charts
$ helm repo update
$ helm upgrade --install baselime-logs-exporter baselime-logs-exporter/baselime-logs-exporter --values baselime-values.secret.yaml -n baselime --create-namespace 
```

