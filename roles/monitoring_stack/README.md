---
description: Monitoring Stack (Prometheus + Grafana)
---

This role installs an optional monitoring stack using Docker Compose:

- Prometheus on port 9090
- Grafana on port 3000

## Enable

Set in your server vars/group_vars:

- `monitoring_stack_enabled: true`
- `monitoring_polymarket_targets`: list of `host:port` strings for the exporters

Example:

```yaml
monitoring_stack_enabled: true
monitoring_polymarket_targets:
  - "127.0.0.1:9110"  # kryetari
  - "127.0.0.1:9111"  # durani
```

Grafana default login: `admin` / `monitoring_grafana_admin_password`.
