FROM ubuntu

RUN apt update
RUN apt install curl -y
RUN apt install python3 -y

COPY . .

RUN pip install flask

CMD python app.py