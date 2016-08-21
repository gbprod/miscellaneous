```bash
sudo apt-get install php7.0 php7.0-cli php7.0-mbstring php7.0-sqlite3
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
sudo php composer-setup.php  --install-dir=/bin  --filename=composer
php -r "unlink('composer-setup.php');"
```
