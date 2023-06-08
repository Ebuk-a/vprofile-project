FROM mysql:8.0.33
LABEL "Author"="Ebuka"
LABEL "Project"="vprofile"

ENV MYSQL_ROOT_PASSWORD="vprodbpass"
ENV MYSQL_DATABASE="accounts"

#any file ending in .sql,.sh, or .sql.gz in docker-entrypoint-initdb.d/ will be executed on start
#so we place our db initialization script there.
ADD db_backup.sql docker-entrypoint-initdb.d/db_backup.sql