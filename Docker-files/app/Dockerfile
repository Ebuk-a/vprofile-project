FROM openjdk:11 AS BUILD_IMAGE
RUN apt update && apt install maven -y
RUN git clone https://github.com/Ebuk-a/vprofile-project.git
RUN cd vprofile-project && git checkout docker && mvn install

FROM tomcat:9-jre11
LABEL "Author"="Ebuka"
LABEL "Project"="vprofile"
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=BUILD_IMAGE ./vprofile/target/vprofile-v2.war /usr/local/tomcat/webapps/root.war
EXPOSE 8080
CMD ["catalina.sh","run"]