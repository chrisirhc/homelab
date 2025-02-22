# Use Python 3 base image
FROM python:3.9-slim

# Set working directory
WORKDIR /app

VOLUME /data
VOLUME /downloads

# Copy the script
COPY download.py .
COPY requirements.txt .

# Install dependencies
RUN pip install -r requirements.txt

# Set environment variables with defaults that can be overridden
ENV LOG_FILE=/data/dropbox.log \
    HASH_TABLE=/data/hashtable.sqlite \
    TARGET_FOLDER=/downloads \
    DB_TOKEN=""

# Entrypoint script
ENTRYPOINT python download.py \
            --log $LOG_FILE \
            --hashtable $HASH_TABLE \
            --target_folder $TARGET_FOLDER \
            --compare_hashes
