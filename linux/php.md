```bash
sudo apt-get install php5 php5-cli
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
sudo php composer-setup.php  --install-dir=/bin  --filename=composer
php -r "unlink('composer-setup.php');"
```
