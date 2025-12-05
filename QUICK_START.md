# Quick Start Guide

## 🚀 Get Started in 5 Minutes

### Prerequisites
- Docker Desktop installed and running
- 8GB RAM available
- Ports 3000, 9090, 5601, 9200 available

### 1. Clone and Navigate
```bash
git clone https://github.com/Gcorinthian/monitoring-stack.git
cd monitoring-stack
```

### 2. Start the Stack
```bash
docker-compose -f docker/compose-files/full-stack.yml up -d
```

### 3. Wait for Services (2-3 minutes)
```bash
# Check status
docker-compose -f docker/compose-files/full-stack.yml ps
```

### 4. Access Dashboards

| Service | URL | Credentials |
|---------|-----|-------------|
| Grafana | http://localhost:3000 | admin/admin |
| Prometheus | http://localhost:9090 | - |
| Kibana | http://localhost:5601 | - |
| Jaeger | http://localhost:16686 | - |

### 5. Import Dashboards
1. Go to Grafana (localhost:3000)
2. Login with admin/admin
3. Navigate to Dashboards → Import
4. Upload JSON files from `grafana/dashboards/`

### 6. View System Metrics
- **CPU Usage**: Grafana → System Overview Dashboard
- **Memory Usage**: Real-time memory consumption
- **Disk Usage**: Available disk space monitoring
- **Network I/O**: Network traffic statistics

## 🛑 Stop the Stack
```bash
docker-compose -f docker/compose-files/full-stack.yml down
```

## 🧹 Clean Up
```bash
# Remove all containers and volumes
docker-compose -f docker/compose-files/full-stack.yml down -v

# Remove downloaded images (optional)
docker system prune -a
```

## 📊 What You Get

### Monitoring Capabilities
- **System Metrics**: CPU, Memory, Disk, Network
- **Application Metrics**: Request rates, error rates, response times
- **Log Aggregation**: Centralized logging with search
- **Distributed Tracing**: Request flow across services
- **Alerting**: Automated notifications for issues

### Enterprise Features
- **High Availability**: Multi-instance deployments
- **Scalability**: Horizontal scaling support
- **Security**: Authentication and authorization
- **Performance**: Optimized for production workloads

## 🔧 Customization

### Add Your Application
1. Update `prometheus/config/prometheus.yml`
2. Add your service endpoints to scrape_configs
3. Restart Prometheus: `docker-compose restart prometheus`

### Custom Dashboards
1. Create JSON files in `grafana/dashboards/`
2. Import via Grafana UI
3. Configure data sources and panels

### Alert Rules
1. Edit `prometheus/rules/alerts.yml`
2. Add custom alert conditions
3. Configure AlertManager for notifications

## 📞 Troubleshooting

### Common Issues
- **Port conflicts**: Change ports in docker-compose.yml
- **Memory issues**: Increase Docker memory limit
- **Slow startup**: Wait longer, check Docker logs

### Check Logs
```bash
# View all logs
docker-compose -f docker/compose-files/full-stack.yml logs

# View specific service logs
docker-compose -f docker/compose-files/full-stack.yml logs grafana
```

### Health Checks
```bash
# Check service health
curl http://localhost:9090/-/healthy  # Prometheus
curl http://localhost:3000/api/health # Grafana
```

## 🎯 Next Steps
1. Explore pre-built dashboards
2. Set up custom alerts
3. Add your applications to monitoring
4. Configure log shipping from your services
5. Set up distributed tracing in your code

---

**Need help? Check the main README.md or create an issue!**
