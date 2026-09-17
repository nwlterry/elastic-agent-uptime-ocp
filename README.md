# elastic-agent-uptime-ocp

OpenShift/Kubernetes manifests for an Elastic Agent Heartbeat/uptime deployment plus a Logstash sidecar path.

## Manifests

| File | Purpose |
| --- | --- |
| `elastic-agent-uptime.yaml` | Deployment, ServiceAccount, SCC RoleBinding, and Fleet enrollment token Secret. Image `elastic-agent:8.15.3`. |
| `elastic-agent-uptime-minimal.yaml` | Smaller variant. |
| `elastic-agent-uptime-complete.yaml` | Complete/synthetics-oriented variant. |
| `logstash-configmap.yaml` | Logstash pipeline ConfigMap. |
| `logstash-deployment.yaml` | Logstash Deployment. |

## Before apply

1. Replace `<YOUR_FLEET_ENROLLMENT_TOKEN_HERE>` in the Secret.
2. Set `FLEET_URL` to your Fleet Server (in-cluster Service or Route).
3. Match the agent image tag to the Elastic Stack version.
4. Namespace in the sample is `heartbeat-ns`.

```bash
kubectl apply -f elastic-agent-uptime.yaml
```

The sample uses `emptyDir` for agent state. Use a PVC if you need state across restarts.
