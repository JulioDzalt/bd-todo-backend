# Production
~~~bash
    $ docker run --rm --name todo-mysql \
    -e MYSQL_ROOT_PASSWORD=root \
    -e MYSQL_DATABASE=todos \
    -v /home/julio/Desktop/bd-todo-backend/data:/var/lib/mysql \
    -d mysql:5.7
~~~

# Development
~~~bash
    $ docker run --rm --name todo-mysql \
    -e MYSQL_ROOT_PASSWORD=root \
    -e MYSQL_DATABASE=todos \
    -v /home/julio/Desktop/bd-todo-backend/data:/var/lib/mysql \
    -d mysql:5.7

    $ docker exec -it {id_container} mysql -p 
~~~

# Script SQL DB

~~~sql
    create database todos;

    use todos;

    CREATE TABLE IF NOT EXISTS todos (
        id INT AUTO_INCREMENT PRIMARY KEY,
        title VARCHAR(255) NOT NULL,
        description TEXT
    );

    select * from todos;

    INSERT INTO todos (title, description) VALUES  ("julio","juliodes");
    INSERT INTO todos (title, description) VALUES  ("juan","juandes");
    INSERT INTO todos (title, description) VALUES  ("ya","jalo");


    CREATE USER 'julio'@'localhost' IDENTIFIED BY 'julio';
    GRANT ALL PRIVILEGES ON * . * TO 'julio'@'localhost';
    GRANT ALL PRIVILEGES ON todos.* TO 'julio'@'localhost' WITH GRANT OPTION;
    FLUSH PRIVILEGES;

~~~