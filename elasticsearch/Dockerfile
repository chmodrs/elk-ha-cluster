FROM docker.elastic.co/elasticsearch/elasticsearch:6.6.0
RUN bin/elasticsearch-plugin install -b repository-s3
RUN mkdir -p /aws

ADD access_key /aws/access_key
ADD secret /aws/secret

RUN \
  cat /aws/access_key | base64 --decode | bin/elasticsearch-keystore add --stdin --force s3.client.default.access_key && \
  cat /aws/secret | base64 --decode | bin/elasticsearch-keystore add --stdin --force s3.client.default.secret_key
