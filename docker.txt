FROM bitnami/dokuwiki:latest
RUN apt-get update && apt-get install wget
RUN cd /bitnami/dokuwiki/lib/plugins 
RUN wget https://github.com/dokufreaks/plugin-tag/archive/2017-08-24.tar.gz
RUN tar -xvf 2017-08-24.tar.gz 
RUN mv plugin-tag-2017-08-24/ tag/ 
RUN chgrp -R daemon tag/ && chown -R daemon tag/
RUN rm 2017-08-24.tar.gz