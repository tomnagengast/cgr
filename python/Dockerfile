# Install dependencies
FROM cgr.dev/chainguard/python:latest-dev AS dev

WORKDIR /app

RUN python -m venv venv
ENV PATH="/app/venv/bin":$PATH
COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt

# Build the application
FROM cgr.dev/chainguard/python:latest

WORKDIR /app

COPY . .
COPY --from=dev /app/venv /app/venv
ENV PATH="/app/venv/bin":$PATH

ENTRYPOINT ["fastapi", "dev", "main.py", "--host", "0.0.0.0"]
