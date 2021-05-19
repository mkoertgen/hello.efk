#
# fluent/fluentd:v1.12.0-debian-1.0
FROM fluent/fluentd:edge

USER root
# https://rubygems.org/gems/fluent-plugin-elasticsearch/
RUN ["gem", "install", "fluent-plugin-elasticsearch", "--no-document", "--version", "5.0.3"]
USER fluent
