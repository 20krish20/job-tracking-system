# ---- Base image ----
FROM python:3.11-slim

# ---- Environment configuration ----
ENV PYTHONDONTWRITEBYTECODE=1 \
    PYTHONUNBUFFERED=1 \
    PORT=8080

# ---- Working directory ----
WORKDIR /app

# ---- Install dependencies ----
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# ---- Copy all code ----
COPY . .

# ---- Functions Framework command ----
# Tell Google Cloud Run which function to serve
CMD ["functions-framework", "--target", "scan_jobs_test", "--port", "8080"]
