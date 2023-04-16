FROM rasa/rasa:3.0.4

USER root

# Copy your Rasa project files
COPY . /app

# Set the working directory
WORKDIR /app

# Install any additional dependencies specified in your requirements.txt
# upgrade pip version
RUN pip install --upgrade pip && \
    pip install -r requirements.txt

COPY ./actions /app/actions

USER 1001

# Expose the Rasa port
EXPOSE 5005

CMD ["rasa", "run", "--enable-api", "-p", "5005", "--cors", "*"]
