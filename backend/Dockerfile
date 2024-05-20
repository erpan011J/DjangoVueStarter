# Use the official Python image with Python 3.10
FROM python:3.10-slim

# Set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# Set the working directory in the container
WORKDIR /app

# Install dependencies
RUN pip install --upgrade pip
COPY ./backend/requirements.txt /app/requirements.txt
RUN pip install -r requirements.txt

# Copy the current directory contents into the container at /app
COPY ./backend /app

# Collect static files
RUN python manage.py collectstatic --noinput

# Run Gunicorn
CMD ["gunicorn", "--bind", "0.0.0.0:8000", "app.wsgi:application"]
