FROM python:3.10

WORKDIR /usr/src/app

COPY . .

RUN pip install --upgrade pip setuptools wheel

RUN pip install -r requirements.txt


CMD ["flask", "run"]

