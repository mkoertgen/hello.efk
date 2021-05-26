#
ARG FLUENTD_VERSION=v1.12.2-debian-1.0
FROM fluent/fluentd:${FLUENTD_VERSION}

USER root
# https://rubygems.org/gems/fluent-plugin-elasticsearch/
RUN ["gem", "install", "--no-document", "fluent-plugin-elasticsearch:5.0.3"]
USER fluent
