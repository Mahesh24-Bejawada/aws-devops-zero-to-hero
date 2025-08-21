# Stage 1: Build stage
FROM python:3.9-slim AS builder

WORKDIR /app

# Copy requirements and install dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy the app source code
COPY app.py .

# Stage 2: Final runtime stage
FROM python:3.9-slim

WORKDIR /app

# Copy only installed python packages from builder stage
COPY --from=builder /usr/local/lib/python3.9/site-packages /usr/local/lib/python3.9/site-packages
COPY --from=builder /app/app.py .

EXPOSE 3000

CMD ["python", "app.py"]
