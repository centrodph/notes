

# Getting the Postgres Docker Image

https://hackernoon.com/dont-install-postgres-docker-pull-postgres-bee20e200198



docker pull postgres


// docker pull postgres:[tag_you_want]


mkdir -p $HOME/docker/volumes/postgres


```

docker run --rm   --name pg-docker -e POSTGRES_PASSWORD=docker -d -p 5432:5432 -v $HOME/docker/volumes/postgres:/var/lib/postgresql/data  postgres


```

psql -h localhost -U postgres -d postgres



URI: postgres://postgres:docker@localhost:5432/postgres



## import sql into docker

```

psql -f ./xxx.sql -U postgres -h localhost


```

# drop schema


```


DROP SCHEMA public CASCADE;
CREATE SCHEMA public;
GRANT ALL ON SCHEMA public TO postgres;
GRANT ALL ON SCHEMA public TO public;


```





# create a user 

https://stackoverflow.com/questions/15301826/psql-fatal-role-postgres-does-not-exist

For MAC:

```
Install Homebrew

brew install postgres

initdb /usr/local/var/postgres

/usr/local/Cellar/postgresql/<version>/bin/createuser -s postgres or /usr/local/opt/postgres/bin/createuser -s postgres 


which will just use the latest version.
start postgres server manually: 
pg_ctl -D /usr/local/var/postgres start
To start server at startup

mkdir -p ~/Library/LaunchAgents
ln -sfv /usr/local/opt/postgresql/*.plist ~/Library/LaunchAgents
launchctl load ~/Library/LaunchAgents/homebrew.mxcl.postgresql.plist
Now, it is set up, login using psql -U postgres -h localhost or use PgAdmin for GUI.

By default user postgres will not have any login password.

Check this site for more articles like this: https://medium.com/@Nithanaroy/installing-postgres-on-mac-18f017c5d3f7


```
