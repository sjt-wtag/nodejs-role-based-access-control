# nodejs-role-based-access-control

# Auth
 
 ```
 api/auth/register
 api/auth/login
 ```


 # User Routes
 
 ```
 api/users/admin
 api/users/manager
 api/users/user
 ```

 # Docker 

```
docker ps \\ will show the container id for app & db

docker exec -it 68e4faed6532 psql -U postgres -d rbacDB \\ docker exec -it <conatainer id of db> psql -U postgres -d <database name>

\dt  \\ check database table


CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    username VARCHAR(255) NOT NULL UNIQUE,
    password VARCHAR(255) NOT NULL,
    role VARCHAR(20) NOT NULL CHECK (role IN ('admin', 'manager', 'user'))
); \\ create databse 


```

Then test end points using postman