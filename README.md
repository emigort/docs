# Instalation php with nginx for php7.4 and laravel 8

        sudo apt update
        sudo apt upgrade
        sudo apt install nginx
        sudo systemctl start nginx.service
        sudo systemctl status nginx
        sudo apt install php7.4 php7.4-fpm php7.4-cli php7.4-gd php7.4-mysql php7.4-curl php7.4-intl php7.4-mbstring php7.4-bcmath php7.4-imap php7.4-xml php7.4-zip
        systemctl status php7.4-fpm
        # Edit nginx configuration 
        sudo nano /etc/nginx/sites-available/default
        # edit default file
        location ~ \.php$ {
                fastcgi_pass unix:/var/run/php/php7.2-fpm.sock;
                fastcgi_index index.php;
                fastcgi_param SCRIPT_FILENAME $realpath_root$fastcgi_script_name;
                include fastcgi_params;
            }
        sudo systemctl restart php7.4-fpm
        sudo systemctl restart nginx
        # sudo apt install php8.0-[extension-name]
        #INSTALL COMPOSER https://getcomposer.org/doc/00-intro.md#installation-linux-unix-macos
