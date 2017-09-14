# ElasticsearchForNetcool

I know this is sloppy, for now it is a dump of my history file to get things
in place.
```
UPDATE"probe_gateway_connection_event:AGG_P:sijr30eoisnco01.noc.envops.ibm:7:GATEWAY:failover_gate:";"sidr30eoisnco01.noc.envops.ibmserviceengage.com";"sidr30eoisnco01.noc.envops.ibmserviceengage.com";"OMNIbus Self Monitoring @AGG_P";"OMNIbus SelfMonitoring";"ConnectionStatus";"";2;"GATEWAY: failover_gate connected from host sijr30eoisnco01.noc.envops.ibm (ID: 7).";2017-09-13T13:59:26-0500;2017-08-15T11:55:11-0500;2017-09-13T13:59:26-0500;2017-09-13T13:59:26-0500;0;13;41877;99999;7;"";65534;0;0;0;"";90;0;0;"";"";0;0;"";0;"";0;0;"";"";"";"";"";"";"";"";0;0;"";"";"";"AGG_P";30221
```
```
cd /opt/IBM/netcool/logstash/
Download mtlumberjack: https://github.ibm.com/LogmetClients/logstash/archive/master.zip
ls
unzip master.zip
ls -latr
file master.zip
cat master.zip
rm master.zip
unzip ~/logstash-master.zip
cd /opt/IBM/netcool/logstash/
ls
java -version
ls
tar xzf server-jre-8u144-linux-x64.tar.gz
/opt/IBM/netcool/logstash/jdk1.8.0_144/bin/java -version
export JAVA_HOME=/opt/IBM/netcool/logstash/jdk1.8.0_144
wget https://artifacts.elastic.co/downloads/logstash/logstash-5.6.0.tar.gz
tar xzf logstash-5.6.0.tar.gz
ls
logstash-5.6.0/bin/logstash -V
cd /opt/IBM/netcool/logstash
cd logstash-master/logstash-output-mtlumberjack-gem/
cat README.md
mkdir -p target/classes
$JAVA_HOME/bin/javac src/SimpleSSLSocket.java
mv src/SimpleSSLSocket.class target/classes
gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3 7D2BAF1CF37B13E2069D6956105BD0E739499BDB
\curl -sSL https://get.rvm.io | bash
source ~/.profile
export PATH=$JAVA_HOME/bin:$PATH
rvm install jruby-1.7.27
rvm use jruby-1.7.27
gem install bundler
cat README.md
gem build logstash-output-mtlumberjack.gemspec
cat README.md
/opt/IBM/netcool/logstash/logstash-5.6.0/bin/logstash-plugin install logstash-output-mtlumberjack-0.1.3.gem
cd /opt/IBM/netcool/logstash/
./logstash-5.6.0/bin/logstash -e 'input { stdin { } } output { mtlumberjack {} }'
```
