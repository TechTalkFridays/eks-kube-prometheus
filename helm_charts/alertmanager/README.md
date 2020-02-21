# Alertmanager

Chart requires that a aws secret is created containing config.ini matching the helm variable secretName

Create the external secret
```bash
aws secretsmanager create-secret --name /engineering/monitoring/alertmanager-main --secret-string file://secret.json
aws secretsmanager update-secret --secret-id /engineering/monitoring/alertmanager-main --secret-string file://secret.json
```

```bash
helm template -n alertmanager . -f helm_vars/morty/values.yaml --namespace monitoring
```
