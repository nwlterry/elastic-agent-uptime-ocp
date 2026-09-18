# elastic-agent-uptime-ocp

OpenShift/Kubernetes manifests for an Elastic Agent Heartbeat/uptime deployment plus Logstash.

## Layout

```
manifests/elastic-agent-uptime.yaml
manifests/elastic-agent-uptime-minimal.yaml
manifests/elastic-agent-uptime-complete.yaml
manifests/logstash-configmap.yaml
manifests/logstash-deployment.yaml
GROUP.md
README.md
```

Before apply: set Fleet enrollment token, `FLEET_URL`, image tag, namespace (`heartbeat-ns` in the sample).

```bash
kubectl apply -f manifests/elastic-agent-uptime.yaml
```

---

See [GROUP.md](GROUP.md) for sibling repositories. Catalog: https://github.com/nwlterry/nwlterry
