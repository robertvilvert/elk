FROM logstash:5.1.1-alpine
# Qualirede

###############################################################################
#                               CONFIGURATION
###############################################################################
# filters
ADD ./02-beats-input.conf /etc/logstash/conf.d/02-beats-input.conf
ADD ./10-syslog.conf /etc/logstash/conf.d/10-syslog.conf
ADD ./11-nginx.conf /etc/logstash/conf.d/11-nginx.conf
ADD ./12-jboss.conf /etc/logstash/conf.d/12-jboss.conf
ADD ./30-output.conf /etc/logstash/conf.d/30-output.conf

# patterns
#ADD ./nginx.pattern ${LOGSTASH_HOME}/patterns/nginx
ADD ./nginx.pattern /usr/share/logstash/vendor/bundle/jruby/1.9/gems/logstash-patterns-core-4.0.2/patterns/nginx
#RUN chown -R logstash:logstash ${LOGSTASH_HOME}/patterns

## Instalando Plugin Beats
#RUN /usr/share/logstash/bin/logstash-plugin install logstash-input-beats

# LogRotate
ADD ./logstash-logrotate /etc/logrotate.d/logstash
RUN chmod 644 /etc/logrotate.d/logstash 

CMD ["-f", "/etc/logstash/conf.d/"]

