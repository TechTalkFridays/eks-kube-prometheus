# Grafana

Chart requires that a aws secret is created containing config.ini matching the helm variable secretName

Create the external secret
```bash
aws secretsmanager create-secret --name /engineering/monitoring/grafana-config --secret-string file://secret.json
aws secretsmanager update-secret --secret-id /engineering/monitoring/grafana-config --secret-string file://secret.json
```

```bash
helm template -n grafana . -f helm_vars/morty/values.yaml --namespace monitoring
```
