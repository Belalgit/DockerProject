FROM mysql:8.0.33
LABEL "Project"="DockerProject"
LABEL "Author"="Belal"

ENV MYSQL_ROOT_PASSWORD="vprodpass"
ENV MYSQL_DATABASE="accounts"

ADD db_backup.sql docker-entrypoint-initdb.d/db_backup.sql


