FROM elasticsearch:5.1.1-alpine
# Qualirede

###############################################################################
#                               CONFIGURATION
###############################################################################

# LogRotate
ADD ./elasticsearch-logrotate /etc/logrotate.d/elasticsearch
RUN chmod 644 /etc/logrotate.d/elasticsearch
