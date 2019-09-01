FROM fluent/fluentd:v1.7-debian-1

# Use root account to use apt
USER root

# below RUN includes plugin as examples elasticsearch is not required
# you may customize including plugins as you wish
RUN buildDeps="make autoconf gcc g++ libc-dev build-essential libgeoip-dev libmaxminddb-dev" \
   && apt-get update \
   && apt-get install -y --no-install-recommends $buildDeps \
   && gem install fluent-plugin-geoip \
   && gem install fluent-plugin-elasticsearch

USER fluent
