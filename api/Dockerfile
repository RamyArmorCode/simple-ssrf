FROM python:3.13.3-slim
WORKDIR /app
COPY requirements.txt app.py ./
RUN pip install -r requirements.txt
# Set a default value for workers in case the environment variable is not set
ENV WORKER_COUNT=4
CMD sh -c "gunicorn --bind 0.0.0.0:8000 --workers ${WORKER_COUNT} app:app"
