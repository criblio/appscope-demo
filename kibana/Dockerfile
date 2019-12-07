RUN curl -Lso /tmp/libscope.so http://cdn.cribl.io/dl/scope/latest/linux/libscope.so && chmod 755 /tmp/libscope.so
ENV LD_PRELOAD=/tmp/libscope.so
ENV SCOPE_METRIC_DEST=udp://cribl-w1:8125
ENV SCOPE_LOG_LEVEL=info
ENV SCOPE_LOG_DEST=file:///tmp/scope.log
ENV SCOPE_METRIC_VERBOSITY=4
ENV SCOPE_EVENT_DEST=tcp://cribl-w0:5140
ENV SCOPE_TAG_service=kibana