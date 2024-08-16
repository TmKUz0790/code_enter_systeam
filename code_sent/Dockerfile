# Use an official Python runtime as a parent image
FROM python:3.10.11-slim

# Set the working directory inside the container
WORKDIR /code_sent_app

# Copy the requirements file into the working directory
COPY requirements.txt /code_sent_app/

# Install the dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of the application code into the working directory
COPY . /code_sent_app/

# Run Django collectstatic to gather static files (only needed if you have static files)
RUN python manage.py collectstatic --noinput

# Expose port 8000 to the outside world
EXPOSE 8000

# Run the application using the Django development server
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
