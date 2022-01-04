FROM redis:latest
ADD entrypoint.sh /sbin/entrypoint.sh
ADD loaddata.sh /sbin/loaddata.sh
ENTRYPOINT ["/sbin/entrypoint.sh"]
ADD session.csv /data/session.csv
CMD ["start"]
RUN apt-get update && apt-get install -y curl ca-certificates --no-install-recommends
RUN VERSION=$(curl -s https://cdn.cribl.io/dl/scope/latest) && \
    curl -Lso /tmp/scope "https://cdn.cribl.io/dl/scope/${VERSION}/linux/x86_64/scope" && \
    chmod 755 /tmp/scope && \
    /tmp/scope excrete /usr/lib/
ENV LD_PRELOAD=/usr/lib/libscope.so
ENV SCOPE_METRIC_DEST=udp://cribl-w0:8125
ENV SCOPE_LOG_LEVEL=info
ENV SCOPE_LOG_DEST=file:///tmp/scope.log
ENV SCOPE_METRIC_VERBOSITY=4
ENV SCOPE_EVENT_DEST=tcp://cribl-w0:5140
ENV SCOPE_TAG_service=redis
