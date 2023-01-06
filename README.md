Criando a rede docker
 - docker network create docker_exercise_network

Criando o volume
 - docker volume create docker_exercise_database_volume

Subindo container do mysql
- docker run -p 3306:3306 -e "MYSQL_ROOT_PASSWORD=teste" --name database --network docker_exercise_network -v docker_exercise_database_volume:/var/lib/mysql mysql:5.7

Subindo PHPMYADMIN
- docker run -p 8080:80 -e "PMA_HOST=database" -e "PMA_PORT=3306" --network docker_exercise_network phpmyadmin/phpmyadmin

