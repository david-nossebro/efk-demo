FROM fluent/fluentd:latest
ADD ./conf/fluent.conf /fluentd/etc/fluent.conf
RUN apk add --update --virtual .build-deps \
    sudo build-base ruby-dev \
    && sudo gem install \
    fluent-plugin-elasticsearch \
    && sudo gem sources --clear-all \
    && apk del .build-deps \
    && rm -rf /var/cache/apk/* /home/fluent/.gem/ruby/2.3.0/cache/*.gem \
    && mkdir /logs \
    && chmod 777 /logs \