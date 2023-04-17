FROM rasa/rasa:3.0.4
WORKDIR '/app'
COPY . /app
USER root
COPY ./data /app/data
COPY ./models /app/models
RUN rasa train
CMD ["run","-m","/app/models","--enable-api","--cors","*","--debug" ,"--endpoints", "endpoints.yml", "--log-file", "out.log", "--debug"]
