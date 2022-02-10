FROM node:lts
ADD . /opt/apiserver
RUN  cd /opt/apiserver && npm install
ADD customer_master_small.csv /data/customer_master_small.csv
CMD ["node","/opt/apiserver/server.js"]
RUN VERSION=$(curl -s http://cdn.cribl.io/dl/scope/latest) && \
    curl -Lso /tmp/scope "https://cdn.cribl.io/dl/scope/${VERSION}/linux/x86_64/scope" && \
    chmod 755 /tmp/scope && \
    /tmp/scope excrete /usr/lib/
ENV LD_PRELOAD=/usr/lib/libscope.so
ENV SCOPE_METRIC_DEST=udp://cribl-w1:8125
ENV SCOPE_LOG_LEVEL=info
ENV SCOPE_LOG_DEST=file:///tmp/scope.log
ENV SCOPE_METRIC_VERBOSITY=5
ENV SCOPE_EVENT_DEST=tcp://cribl-w0:5140
ENV SCOPE_TAG_service=apiserver
