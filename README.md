## Container Documentation for Haproxy Documentation

The CleanStart Haproxy image provides a high-performance, security-hardened web server optimized for enterprise environments. Built with minimal attack surfaces and comprehensive security hardening, this image delivers reliable web serving capabilities with advanced security features.

📌 **Base Foundation**: Production-ready container from cleanstart.

**Image Path**: `ghcr.io/cleanstart-containers/haproxy`

**Registry**: cleanstart Registry

## Pull Latest Image
Download the container image from the registry

```bash
docker pull ghcr.io/cleanstart-containers/haproxy:latest
```
```bash
docker pull ghcr.io/cleanstart-containers/haproxy:latest-dev
```

## Basic Run
Run the container with basic configuration

```bash
docker run -it --name haproxy ghcr.io/cleanstart-containers/haproxy:latest
```

## Production Deployment
Deploy with production security settings

```bash
docker run -d --name haproxy-prod \
  --security-opt=no-new-privileges \
  --user 1000:1000 \
  --restart unless-stopped \
  ghcr.io/cleanstart-containers/haproxy:latest
```

Volume Mount Mount local directory for persistent data

```bash
docker run -v /app:/app ghcr.io/cleanstart-containers/haproxy:latest
```

Port Forwarding Run with custom port mappings

```bash
docker run -p 8080:8080 ghcr.io/cleanstart-containers/haproxy:latest
```

## Environment Variables
Configuration options available through environment variables

| Variable | Default | Description |
|----------|---------|-------------|
| ENV | production | Environment mode |
| LOG_LEVEL | info | Logging level |

## Kubernetes Security Context
Recommended security context for Kubernetes deployments

```yaml
securityContext:
  allowPrivilegeEscalation: false
  capabilities:
    drop:
    - ALL
  readOnlyRootFilesystem: true
  runAsUser: 1000
  runAsGroup: 1000
```

## Documentation Resources
Essential links and resources for further information
 
**CleanStart Images**: https://images.cleanstart.com/
 
**Community Images**:
**Docker Hub**: https://hub.docker.com/u/cleanstart<br>
**GitHub**: https://github.com/cleanstart-containers<br>
**AWS ECR Public Gallery**: https://gallery.ecr.aws/cleanstart/
 
**Presence on Social Media**:
**Community**: https://www.linkedin.com/groups/18324021/<br>
**YouTube**: https://www.youtube.com/@CleanStartOfficial<br>
 
**Contribute to Container Use Cases**: https://github.com/cleanstart-dev/cleanstart-use-cases/
