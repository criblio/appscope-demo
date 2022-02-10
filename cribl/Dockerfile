FROM cribl/cribl:latest
RUN /opt/cribl/bin/scope excrete /usr/lib/
ENV LD_PRELOAD=/usr/lib/libscope.so
ENV SCOPE_METRIC_DEST=udp://cribl-w1:8125
ENV SCOPE_LOG_LEVEL=info
ENV SCOPE_LOG_DEST=file:///tmp/scope.log
ENV SCOPE_METRIC_VERBOSITY=4
ENV SCOPE_TAG_service=cribl
