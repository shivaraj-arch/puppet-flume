1. login to machine 
2. download the apache flume binary from site. if you have larger RAM then compile src with mvn and build binary.
3. create a init.d script for the flume. 
4. cd /etc/puppet
5. sudo puppet apply manifests/site.pp (for usage as configuration for applying puppet.)
6. telnet localhost 44444 
7. from another terminal : tail -f /home/ubuntu/apache-flume-1.4.0-bin/logs/flume.log
8. all that typed in telnet session will be logged on the configured log file flume.log if you included this in init.d script : 
<code> bin/flume agent --conf conf --conf-file conf/example.conf --name a1 -Dflume.root.logger=INFO,console </code>
 where a1 is flume agent with example.conf defining the source channel and sink for logger console session.
