alias micro='ssh -i ./micro.pem ec2-user@52.91.122.158'
ssh -i ~/nutch_key.pem azureuser@13.82.177.96

export JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk-1.8.0.252.b09-2.amzn2.0.1.x86_64/jre
export PATH=$JAVA_HOME/bin:$PATH

sudo yum install java-1.8.0-openjdk-devel

https://cwiki.apache.org/confluence/pages/viewpage.action?pageId=115515088#NutchTutorial-SetupSolrforsearch
export APACHE_SOLR_HOME=/home/ec2-user/solr-7.7.3
mkdir -p ${APACHE_SOLR_HOME}/server/solr/configsets/nutch/
cp -r ${APACHE_SOLR_HOME}/server/solr/configsets/_default/* ${APACHE_SOLR_HOME}/server/solr/configsets/nutch/

export APACHE_SOLR_HOME=/home/ec2-user/solr-7.7.3
cp ./schema.xml ${APACHE_SOLR_HOME}/server/solr/configsets/nutch/conf/


ssh -i micro.pem -L 5000:127.0.0.1:8983 ec2-user@3.94.211.204 


nohup bin/nutch fetch $s1 > foo &


bin/nutch index crawl/crawldb/ -linkdb crawl/linkdb/ $s3 -filter -normalize -deleteGone


## Anaya scraping workflow start
docker run -t -i -d --name nutchcontainer apache/nutch /bin/bash
docker attach --sig-proxy=false nutchcontainer
docker run -t -i -d --name nutchcontainer1-18 apache/nutch:release-1.18 /bin/bash
docker attach --sig-proxy=false nutchcontainer1-18

docker run -v /root/nutch/crawl:/tmp/crawl -t -i -d --name nutchcontainer1-18 apache/nutch:release-1.18 /bin/bash

