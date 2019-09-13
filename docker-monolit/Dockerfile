FROM ubuntu:16.04
RUN apt-get update && apt-get install -y git 
RUN git clone  https://github.com/express42/reddit.git
RUN apt-get -y install mongodb-server ruby-full ruby-dev build-essential git
RUN gem install bundler
COPY mongod.conf /etc/mongod.conf
COPY db_config /reddit/db_config
COPY start.sh /start.sh
RUN cd /reddit && bundle install
RUN chmod 0777 /start.sh
CMD ["/start.sh"]

