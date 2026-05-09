ARG N8N_VERSION=stable

FROM docker.n8n.io/n8nio/n8n:${N8N_VERSION}

LABEL maintainer="Dav <dav@igmachine.dev>"

# ===== ENVIRONMENT VARIABLES =====
ENV N8N_ENFORCE_SETTINGS_FILE_PERMISSIONS=true \
    N8N_RUNNERS_ENABLED=true \
    N8N_PROXY_HOPS=1 \
    N8N_DIAGNOSTICS_ENABLED=false \
    N8N_HIRING_BANNER_ENABLED=false \
    N8N_TEMPLATES_ENABLED=false \
    N8N_PERSONALIZATION_ENABLED=false

# ===== INSTALL SYSTEM DEPENDENCIES =====
USER root

# Install Chromium dependencies for Playwright
RUN apk add --no-cache \
    chromium \
    nss \
    freetype \
    harfbuzz \
    ca-certificates \
    ttf-freefont \
    font-noto-emoji \
    python3 \
    make \
    g++ \
    curl \
    bash \
    tini

# ===== INSTALL PLAYWRIGHT =====
ENV PLAYWRIGHT_BROWSERS_PATH=/usr/bin/chromium
ENV PLAYWRIGHT_CHROMIUM_EXECUTABLE_PATH=/usr/bin/chromium/chrome

# ===== INSTALL COMMUNITY NODES =====
RUN cd /usr/local/lib/node_modules/n8n && \
    npm install n8n-nodes-playwright || true

# ===== SET PERMISSIONS =====
# HuggingFace runs containers as user ID 1000
USER node

# Create necessary directories
RUN mkdir -p /home/node/.n8n

# n8n default port
EXPOSE 5678

# ===== ENTRYPOINT =====
ENTRYPOINT ["tini", "--", "/docker-entrypoint.sh"]
