FROM python:3.10-bullseye


WORKDIR /app


COPY . .


COPY requirements.txt .


RUN pip install --no-cache-dir -r requirements.txt


EXPOSE 8080


CMD ["uvicorn", "spaceship.app:app", "--host", "0.0.0.0", "--port", "8080"]