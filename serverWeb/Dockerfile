
# Instalar o apache, PHP e suas extensões para uso do mysql. Máquina também atualizada
FROM php:8.2-apache

RUN apt-get update && \
    apt-get upgrade -y && \
    docker-php-ext-install mysqli pdo pdo_mysql && \
    rm -rf /var/lib/apt/lists/*

# Habilitar mod_rewrite do Apache, exemplo de uso, alteração das URLs de acesso
RUN a2enmod rewrite

# Copia os arquivos de crud app para o diretório Apache do container criado
# COPY ../crud-app /var/www/html/

# Permissionando para funcionamento correto
RUN chown -R www-data:www-data /var/www/html
RUN chmod -R 755 /var/www/html

# Deixando porta 80 visível para mapeamento no docker-composer
EXPOSE 80
