FROM grafana/loki:latest

USER root


RUN mkdir -p /loki/chunks \
    /loki/rules \
    /loki/tsdb-index \
    /loki/tsdb-cache \
    /loki/compactor \
    && chown -R 10001:10001 /loki

# Go back to loki user
USER 10001
