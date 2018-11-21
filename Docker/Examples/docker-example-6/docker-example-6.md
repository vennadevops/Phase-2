#### Step-1: Run the mysql db container

    docker run -d --name db -e MYSQL_ROOT_PASSWORD=simple -e MYSQL_DATABASE=firstdb -e MYSQL_USER=user -e MYSQL_PASSWORD=pass123 mysql

#### Step-2: Connect to the db container and create tables

    docker exec -it db bash

    mysql -h 127.0.0.1 -P 3306 -uuser -ppass123 firstdb

    CREATE TABLE Persons (PersonID int, LastName varchar(255), FirstName varchar(255), Address varchar(255), City varchar(255) );

    INSERT INTO Persons (PersonID, LastName, FirstName, Address, City) VALUES (1, 'Sureshkumar', 'Deepak', 'Jackal Creek','Johannesburg');

#### Step-3: 

    docker build -t javadbapp .

docker run --name linkcontainers --link db javadbapp
