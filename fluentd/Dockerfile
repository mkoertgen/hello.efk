#
# fluent/fluentd:v1.12.0-debian-1.0
FROM fluent/fluentd:edge

USER root
RUN ["gem", "install", "fluent-plugin-elasticsearch", "--no-document", "--version", "4.3.3"]
USER fluent
