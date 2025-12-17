# Infrastructure Dashboards

This directory contains Grafana dashboards for infrastructure monitoring.

## Available Dashboards

- **System Overview**: CPU, Memory, Disk, Network metrics
- **Kubernetes Cluster**: Pod, Service, Ingress monitoring  
- **Docker Containers**: Container resource usage
- **Database Performance**: MySQL, PostgreSQL, MongoDB metrics

## Usage

Import these JSON files into Grafana:
1. Go to Grafana UI → Dashboards → Import
2. Upload the JSON file
3. Configure data source (Prometheus)
4. Save dashboard

## Customization

Each dashboard can be customized for your environment:
- Update data source names
- Modify alert thresholds
- Add custom panels
- Adjust time ranges
