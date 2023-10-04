# FROM maven:3.8.6-openjdk-8
# RUN apt update && git clone https://github.com/wakaleo/game-of-life.git
# RUN cd game-of-life && mvn package

# FROM tomcat:9.0
# COPY --from=build /game-of-life/gameoflife-web/target/gameoflife.war  /usr/local/tomcat/webapps/gameoflife.war
# EXPOSE 8080
# CMD ["catalina.sh", "run"]


FROM openjdk-8-jdk 
RUN apt update && https://github.com/wakaleo/game-of-life.git
RUN cd game-of-life && mvn package

FROM tomcat:9.0
COPY