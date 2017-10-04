alpine latest with latest filebeat

configuration:
- filebeat.yml: add necessary log sources
- logstash host settings can be passed during container run: docker run -it -e LOGSTASH_HOST=%YOUR_HOST% -d tst-filebeat
