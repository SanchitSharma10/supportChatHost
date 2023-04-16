# Use the official Miniconda3 image as the base
FROM continuumio/miniconda3

# Set the working directory
WORKDIR /app

# Copy your Rasa project files
COPY . /app

# Copy the environment.yml file into the container
COPY environment.yml .

# Update conda and install the dependencies from the environment.yml file
RUN conda update -n base -c defaults conda && \
    conda env update -f environment.yml && \
    conda clean -afy

# Install any additional dependencies specified in your requirements.txt
# upgrade pip version
RUN pip install --no-cache-dir --upgrade pip

# Install the specified packages from GitHub
RUN pip install git+https://github.com/vpol/text.git --no-deps && \
    pip install git+https://github.com/RasaHQ/rasa-sdk@3.0.2 --no-deps && \
    pip install git+https://github.com/RasaHQ/rasa.git@3.0.4 --no-deps

# Expose the Rasa port
EXPOSE 5005
