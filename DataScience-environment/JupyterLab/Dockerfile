FROM python:3.11-slim

WORKDIR /workspace

# Optional: system tools for scientific libraries
RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

# Copy external requirements file
COPY requirements.txt .

# Install all Python dependencies (JupyterLab included)
RUN pip install --no-cache-dir -r requirements.txt

EXPOSE 8888

CMD ["jupyter", "lab", "--ip=0.0.0.0", "--no-browser", "--allow-root"]
