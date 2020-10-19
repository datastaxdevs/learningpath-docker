FROM python:3.7-slim
MAINTAINER "Maintainer Name <Maintainer Email>"
RUN apt-get update 
RUN apt-get install -y --no-install-recommends wget
# Dumb init
RUN wget -O /usr/local/bin/dumb-init https://github.com/Yelp/dumb-init/releases/download/v1.2.0/dumb-init_1.2.0_amd64
RUN chmod +x /usr/local/bin/dumb-init
RUN pip install --upgrade pip
WORKDIR /usr/src/app
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY app.py .
ENV FLASK_APP=app.py FLASK_ENV=development
ENTRYPOINT ["/usr/local/bin/dumb-init", "flask", "run", "--host=0.0.0.0"]
