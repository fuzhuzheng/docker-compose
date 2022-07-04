FROM python:3.8.5

COPY requirements.txt .
RUN buildDeps=' \
# Add some build dependencies here which we can remove later
        ' \
    && apt-get update \
    && apt-get install -y \
        $buildDeps \
        --no-install-recommends \
    && rm -rf /var/lib/apt/lists/* \
    && pip install --no-cache-dir -r requirements.txt \
    && apt-get purge --auto-remove $buildDeps

COPY example_project /code
WORKDIR /code

EXPOSE 8080