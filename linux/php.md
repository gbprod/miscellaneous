```bash
sudo apt-get install php7.0 php7.0-cli php7.0-mbstring php7.0-sqlite3 php7.0-dom php7.0-mysql
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
sudo php composer-setup.php  --install-dir=/bin  --filename=composer
php -r "unlink('composer-setup.php');"
```
