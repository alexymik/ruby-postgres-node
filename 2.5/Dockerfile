FROM ruby:2.5.1
RUN apt-get update \
  && apt-get install -y postgresql postgresql-contrib \
  && apt-get install -y nodejs sudo \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* \
  && sed -i 's/peer/trust/' `find /etc/postgresql  -name "pg_hba.conf"` \
  && sed -i 's/md5/trust/' `find /etc/postgresql  -name "pg_hba.conf"`
#  && /etc/init.d/postgresql start

# This Dockerfile doesn't need to have an entrypoint and a command
# as Bitbucket Pipelines will overwrite it with a bash script.
