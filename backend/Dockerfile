# Use Python 3.12.2 image based on Debian Bullseye in its slim variant as the base image
FROM python:3.12.2-slim-bullseye

# Set an environment variable to unbuffer Python output, aiding in logging and debugging
ENV PYTHONBUFFERED=1

ENV PORT 8000

# Set the working directory within the container to /app for any subsequent commands
WORKDIR /app/backend

# Copy the entire current directory contents into the container at /api/
COPY . /app/backend

# Upgrade pip to ensure we have the latest version for installing dependencies
RUN pip install --upgrade pip

# Install dependencies from the requirements.txt file to ensure our Python environment is ready
RUN pip install -r requirements.txt

# Set the command to run our web service using Gunicorn, binding it to 0.0.0.0 and the PORT environment variable
# CMD gunicorn server.wsgi:application --bind 0.0.0.0:"${PORT}"
CMD python manage.py runserver 0.0.0.0:8000

