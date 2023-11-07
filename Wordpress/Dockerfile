# Use a imagem oficial do WordPress como base
FROM wordpress:latest

# Define informações de configuração do banco de dados como variáveis de ambiente
ENV DB_NAME=******* \
    DB_USER=*********** \
    DB_PASSWORD=*************** \
    DB_HOST=****************** \
    DB_PORT=****

# Crie um arquivo wp-config.php personalizado
RUN { \
        echo "<?php"; \
        echo "define('DB_NAME', '$DB_NAME');"; \
        echo "define('DB_USER', '$DB_USER');"; \
        echo "define('DB_PASSWORD', '$DB_PASSWORD');"; \
        echo "define('DB_HOST', '$DB_HOST');"; \
        echo "define('DB_PORT', '$DB_PORT');"; \
        cat /var/www/html/wp-config-sample.php; \
    } > /var/www/html/wp-config.php

# Expor a porta em que o servidor web do WordPress irá escutar
EXPOSE 80

# Comando para iniciar o servidor web do WordPress
CMD ["apache2-foreground"]
