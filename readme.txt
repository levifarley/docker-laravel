# Clone this repo and initialize Laravel project using git in 'src' directory

# Ensure Laravel project's .env file is correct in the src directory:

    APP_URL=http://localhost:8080
    DB_HOST=mysql
    DB_DATABASE= *Project's database name*

# Ensure '/src/storage' directory is full permissions in container
    
    chmod 777 -R src/storage

# Create network for containers to run on and link up with database container

    docker network create work
    docker network ls

# Start docker

    sudo docker-compose up -d --build

# Run these commands below manually for each project
    
    sudo docker-compose run --rm composer update --no-scripts
    sudo docker-compose run --rm artisan key:generate
    sudo docker-compose run --rm npm install

# Containers created and their ports (if used) are as follows:

    nginx - :8080
    php - :9000
    npm
    composer
    artisan


