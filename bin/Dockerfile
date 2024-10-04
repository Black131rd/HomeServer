FROM python:3.11-alpine
WORKDIR /usr/src/app
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1
RUN apk add --no-cache netcat-openbsd
RUN pip install --upgrade pip
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY entrypoint.sh .
RUN chmod +x entrypoint.sh
COPY . .
ENTRYPOINT ["/bin/sh", "/usr/src/app/entrypoint.sh"]
