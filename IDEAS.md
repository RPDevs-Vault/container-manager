# 💡 Container Management Ideas

Roadmap for the **RPDevs-Vault** container infrastructure.

## 📊 Monitoring & Reporting
- [ ] **GHCR Global Auditor:** Generate a weekly markdown report of all packages in the organization registry.
- [ ] **Vulnerability Scanner:** Integration with `Trivy` or `Gripe` to scan internal images for high/critical CVEs.

## 🧹 Lifecycle & Storage
- [ ] **Stale Package Cleanup:** Automatic deletion of untagged images and versions older than 90 days.
- [ ] **Artifact Transfer:** Move compiled binaries from standard GH Actions to versioned OCI artifacts.

## 🔄 Archival & Mirroring
- [ ] **OCI Mirroring Engine:** Automatically pull critical external images (e.g., from Docker Hub) and push them to `ghcr.io/RPDevs-Vault` to prevent "registry rot" or pull-rate limits.
- [ ] **Base Image Standardizer:** Maintain a set of secure, vetted base images for all infrastructure projects.
