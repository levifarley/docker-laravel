# Clone this repo and initialize Laravel project using git in 'src' directory

# Ensure Laravel project's .env file is correct in the src directory:

    APP_URL=http://localhost:8080
    DB_HOST=mysql
    DB_DATABASE= *Project's database name*

# If anything needs acess to our laravel container (like as an API), use IPV6 address [::1] instead of 'localhost' for routing to work properly

# Ensure '/src/storage' directory is full permissions in container
    
    chmod 777 -R src/storage

# Start docker

    sudo docker-compose up -d --build

# Run these commands below manually for each project
    
    sudo docker-compose run --rm composer update --no-scripts
    sudo docker-compose run --rm artisan key:generate
    sudo docker-compose run --rm npm install

# Containers created and their ports (if used) are as follows:

    nginx - :8080
    php - :9000
    phpMyAdmin - :8081
    npm
    composer
    artisan


