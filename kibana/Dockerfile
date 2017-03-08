FROM kibana:5.1.1
# Qualirede


###############################################################################
#                               CONFIGURATION
###############################################################################

RUN rm -f /etc/kibana/kibana.yml
ADD ./kibana.yml /etc/kibana/kibana.yml


# LogRotate
ADD ./kibana-logrotate /etc/logrotate.d/kibana
RUN chmod 644 /etc/logrotate.d/kibana
