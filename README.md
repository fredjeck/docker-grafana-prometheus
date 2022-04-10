# Grafana and Docker for local monitoring

This is a simple docker compose environment allowing to run a Grafana+Prometheus instance locally to monitor local process while developing.

For instance, if you have a Prometheus enabled application locally on port 5016, add the following snippet to prometheus/configuration/prometheus.yml
```yaml
  - job_name: 'dotnet'
    scrape_interval: 5s
    static_configs:
      - targets: ['host.docker.internal:5016']
```

This repository is hugely a simplification based on [https://github.com/stefanprodan/dockprom](https://github.com/stefanprodan/dockprom)