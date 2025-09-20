# Python backend service Dockerfile
FROM python:3.11-slim

ENV PYTHONDONTWRITEBYTECODE=1 \
    PYTHONUNBUFFERED=1 \
    PIP_NO_CACHE_DIR=1

WORKDIR /app

# Install deps first (better layer caching)
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of the service
COPY . .

# Expose the app port (compose/k8s can remap)
EXPOSE 8000

# Start the API (FastAPI/Starlette layout: app/main.py with "app")
CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8000"]
