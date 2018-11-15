FROM ruby:2.5.1
RUN apt-get update \
  && apt-get install -y postgresql postgresql-contrib \
  && apt-get install -y curl sudo \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* \
  && sed -i 's/peer/trust/' `find /etc/postgresql  -name "pg_hba.conf"` \
  && sed -i 's/md5/trust/' `find /etc/postgresql  -name "pg_hba.conf"`
#  && /etc/init.d/postgresql start

RUN curl -sL https://deb.nodesource.com/setup_6.x | bash

RUN apt-get install -y nodejs

RUN curl -sL https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add - \ 
     echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list \
     apt-get update && apt-get install yarn \
