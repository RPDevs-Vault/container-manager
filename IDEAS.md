# 💡 Fleet Stability Refactoring Ideas (V2)

The following ideas are derived from the **GitHub Build Fleet: Architecture & Infrastructure Guide (V2)** to improve performance, security, and resource management.

### 🛡️ Security & Integrity
- **[PENDING] Verified Base Image Pipeline:** Create a master workflow to build and host hardened Alpine/Ubuntu base images in GHCR. All other machines should use `FROM ghcr.io/rpdevs-vault/base-*` to ensure security and layer caching.
- **[DONE] Pre-Flight Validation:** Validate Dockerfile syntax and environment health before starting heavy builds.
- **[DONE] Runner Housekeeping:** Weekly automated pruning of Docker layers and build artifacts on self-hosted runners.

### 🚀 Performance & Resource Management
- **[PENDING] Shared Compiler Cache (Ccache):** Implement a global ccache mount for builders that compile heavy C++/Go projects (like `go-ethereum` or `FlareSolverr`).
- **[DONE] Dynamic Runner Routing:** Automatically detect if `vault-builder-local` is online and fallback to GitHub Cloud if needed.
- **[PENDING] Tiered Artifact Management:** Separate heavy binary storage into a dedicated "Distributor" repository to keep the main repo clones fast.

### 🏛️ Professionalism & Governance
- **[PENDING] Organization Dispatch Hub:** Use `vault-manager` as a Tier 1 orchestrator that triggers `container-manager` jobs only when new repositories are added or updated.
- **[PENDING] Fleet Status Aggregator:** Create a `fleet-status.json` in the organization hub to provide real-time dashboards of all build outcomes.
- **[DONE] Standardized Metadata:** Ensure every container project has a README and execution command script for easy deployment.
