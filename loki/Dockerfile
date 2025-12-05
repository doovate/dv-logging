FROM alpine:latest AS builder




RUN mkdir -p /loki/chunks \
    /loki/rules \
    /loki/tsdb-index \
    /loki/tsdb-cache \
    /loki/compactor \
    /loki/boltdb-shipper-cache \
    && chown -R 10001:10001 /loki \
    && chmod -R 755 /loki


FROM grafana/loki:latest

COPY --from=builder --chown=10001:10001 /loki /loki

# Go back to loki user
USER 10001

EXPOSE 3100 9096
