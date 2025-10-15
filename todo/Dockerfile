FROM python:3.12-slim AS builder
WORKDIR /app
COPY note.txt .

RUN pip install --no-cache-dir --prefix=/install -r note.txt

FROM python:3.12-slim
WORKDIR /app
COPY --from=builder /install /usr/local
COPY . .
COPY note.txt .
EXPOSE 8000

# Run the app
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
