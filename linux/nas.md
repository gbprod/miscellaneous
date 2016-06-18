# Mounting nas

```bash
sudo apt-get install cifs-utils
sudo mkdir /mnt/data
touch ~/.nas_credencials
echo "username=*****" > ~/.nas_credencials
echo "password=*****" >> ~/.nas_credencials
echo "//192.168.0.10/Volume_1 /mnt/data cifs credentials=/home/gilles/.nas_credencials,iocharset=utf8,noperm,auto 0 0" | sudo tee -a /etc/fstab
sudo mount -a
```
