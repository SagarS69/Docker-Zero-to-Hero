FROM ubuntu

WORKDIR /app

COPY requirements.txt /app/
COPY devops /app/

RUN apt-get update && apt-get install -y python3 python3-pip python3-venv

SHELL ["/bin/bash", "-c"]

RUN python3 -m venv venv1 && \
source venv1/bin/activate && \
pip install --no-cache-dir -r requirements.txt

EXPOSE 8000

CMD source venv1/bin/activate && python3 manage.py runserver 0.0.0.0:8000

#/* or use this simplified Docker code
# Use official Python image based on Ubuntu
#FROM python:3.10-slim

# Set working directory inside the container
#WORKDIR /app

# Copy dependency file first (for better Docker cache usage)
#COPY requirements.txt .

# Create virtual environment and install dependencies
#RUN python -m venv venv && \
    . venv/bin/activate && \
    pip install --upgrade pip && \
    pip install --no-cache-dir -r requirements.txt

# Copy the rest of your app code
#COPY devops/ .

# Expose the Django development server port
#EXPOSE 8000

# Run the Django app using venv Python
#CMD ["venv/bin/python", "manage.py", "runserver", "0.0.0.0:8000"]
#*/





