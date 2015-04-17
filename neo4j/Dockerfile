## Neo4J dependency: java
## get java from official repo
from java:latest
maintainer zhangyh, zyh226@gmail.com

## install neo4j according to http://www.neo4j.org/download/linux
# Import neo4j signing key
# Create an apt sources.list file
# Find out about the files in neo4j repo ; install neo4j community edition

run wget -O - http://debian.neo4j.org/neotechnology.gpg.key | apt-key add - && \
    echo 'deb http://debian.neo4j.org/repo stable/' > /etc/apt/sources.list.d/neo4j.list && \
    apt-get update ; apt-get install neo4j-enterprise=1.9.4 -y

## add launcher and set execute property
## clean sources
## turn on indexing: http://chrislarson.me/blog/install-neo4j-graph-database-ubuntu
## enable neo4j indexing, and set indexable keys to name,age
# enable shell server on all network interfaces
copy conf /var/lib/neo4j/conf
copy launch.sh /
run chmod +x /launch.sh && \
    apt-get clean 
   

# expose REST and shell server ports
expose 7474
expose 1337

workdir /

## entrypoint
cmd ["/bin/bash", "-c", "/launch.sh"]
