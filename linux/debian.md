# Sudoers

```bash
su -c "adduser gilles sudo"
```

restart

```bash
sudo apt-get update
```

# Terminal


```bash
sudo apt-get install terminator curl git vim zsh
chsh -s $(which zsh)

sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

sed -i 's/^plugins=.*/plugins=(git bower composer debian nyan sublime symfony2 docker taskwarrior)/' ~/.zshrc

git clone https://github.com/bhilburn/powerlevel9k.git ~/.oh-my-zsh/custom/themes/powerlevel9k
sed -i 's/^ZSH_THEME=.*/ZSH_THEME="powerlevel9k\/powerlevel9k"/' ~/.zshrc

source ~/.zshrc
 
```
