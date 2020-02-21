# Prometheus

Chart requires that a aws secret is created containing additional-scrape-config matching the helm variable secretName

Create the external secret
```bash
aws secretsmanager create-secret --name /engineering/monitoring/prometheus-additional-scrape --secret-string file://secret.json
aws secretsmanager update-secret --secret-id /engineering/monitoring/prometheus-additional-scrape --secret-string file://secret.json
```

```bash
helm template -n prometheus . -f helm_vars/morty/values.yaml --namespace monitoring
```
