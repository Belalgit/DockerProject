FROM openjdk:11 AS BUILD_IMAGE
RUN apt update && apt install maven -y
RUN git clone https://github.com/Belalgit/DockerProject.git
RUN cd DockerProject && git checkout docker && mvn install

FROM tomcat:9-jre11
LABEL "Project"="DockerProject"
LABEL "Author"="Belal"
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=BUILD_IMAGE DockerProject/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080
CMD ["catalina.sh", "run"]
