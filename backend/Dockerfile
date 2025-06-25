RUN python3 -m venv /opt/venv \
    && /opt/venv/bin/pip install --upgrade pip \
    && /opt/venv/bin/pip install -r requirements.txt



FROM python:3.9-slim

# Install distutils
RUN apt-get update && apt-get install -y python3-distutils

# Set work directory
WORKDIR /app

# Install dependencies
COPY requirements.txt .
RUN pip install -r requirements.txt

# Copy application files
COPY . .

# Set the command to run the application
CMD ["python", "app.py"]
