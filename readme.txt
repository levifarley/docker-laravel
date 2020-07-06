docker-compose up -d --build

# Ensure Laravel project's .env file is correct:
    APP_URL=http://localhost:8080
    DB_HOST=mysql
    DB_DATABASE= *Project's database name*

# If anything needs acess to our laravel container (like as an API), use IPV6 address [::1] instead of 'localhost' for routing to work properly

# Ensure '/src/storage' directory is full permissions in container (chmod 777 -R storage)

# Run these commands below manually

    docker-compose run --rm composer update
    docker-compose run --rm artisan key:generate
    docker-compose run --rm npm install

# For importing databases manually

    * Attach to mysql container -
        'set global max_allowed_packet=268435456;' (Keeps from timing out on imports)
        GRANT ALL PRIVILEGES ON *.* TO 'homestead'@'%';

    * Copy sql files to root project directory for access by Docker

    docker exec -i mysql mysql -uroot -psecret dbName < fileName.sql

# Containers created and their ports (if used) are as follows:

    nginx - :8080
    mysql - :3306
    php - :9000
    npm
    composer
    artisan

# phpmyadmin - Attach to container via browser

    host: mysql
    user: root
    pass: secret
