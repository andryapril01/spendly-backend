FROM python:3.9-slim

# Install distutils and other dependencies
RUN apt-get update && apt-get install -y python3-distutils python3-venv

# Set working directory
WORKDIR /app

# Copy requirements.txt and install dependencies
COPY requirements.txt .
RUN python3 -m venv /opt/venv \
    && /opt/venv/bin/pip install --upgrade pip \
    && /opt/venv/bin/pip install -r requirements.txt

# Copy the rest of the application files
COPY . .

# Set the command to run the application
CMD ["/opt/venv/bin/python", "app.py"]

