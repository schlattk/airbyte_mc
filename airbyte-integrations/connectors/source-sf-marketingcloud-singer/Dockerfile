FROM python:3.7-slim

# Bash is installed for more convenient debugging.
RUN apt-get update -y && apt-get install -y bash && apt-get install -y gcc && rm -rf /var/lib/apt/lists/*

WORKDIR /airbyte/integration_code
COPY source_sf_marketingcloud_singer ./source_sf_marketingcloud_singer
COPY main.py ./
COPY setup.py ./
RUN pip install .

ENV AIRBYTE_ENTRYPOINT "python /airbyte/integration_code/main.py"
ENTRYPOINT ["python", "/airbyte/integration_code/main.py"]

LABEL io.airbyte.version=0.1.0
LABEL io.airbyte.name=airbyte/source-sf-marketingcloud
