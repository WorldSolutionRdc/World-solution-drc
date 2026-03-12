cat > README.md << 'EOF'
# Proxy V2Ray pour VPS 204.48.24.130

Proxy Nginx déployé sur Google Cloud Run pour rediriger le trafic vers le VPS principal.

## Configuration
- **VPS cible** : 204.48.24.130:443
- **Port d'écoute** : 8080
- **Région Cloud Run** : us-central1 (Iowa, USA)
- **Type de proxy** : TCP Stream (layer 4)

## Déploiement
```bash
# Déploiement sur Cloud Run (région USA)
gcloud run deploy v2ray-proxy \
  --source . \
  --platform managed \
  --region us-central1 \
  --allow-unauthenticated \
  --port 8080 \
  --memory 256Mi \
  --timeout 3600
