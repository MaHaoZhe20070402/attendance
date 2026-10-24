FROM tomcat:9.0-jdk11-corretto

RUN rm -rf /usr/local/tomcat/webapps/*

COPY attendance.war /usr/local/tomcat/webapps/attendance.war

COPY entrypoint.sh /usr/local/tomcat/bin/entrypoint.sh
RUN chmod +x /usr/local/tomcat/bin/entrypoint.sh

EXPOSE 8080
CMD ["/usr/local/tomcat/bin/entrypoint.sh"]
