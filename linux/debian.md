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
sudo apt-get install terminator curl git vim zsh fonts-powerline fonts-font-awesome
chsh -s $(which zsh)

sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

sed -i 's/^plugins=.*/plugins=(git bower composer debian nyan sublime symfony2 docker taskwarrior)/' ~/.zshrc

git clone https://github.com/bhilburn/powerlevel9k.git ~/.oh-my-zsh/custom/themes/powerlevel9k
sed -i 's/^ZSH_THEME=.*/ZSH_THEME="powerlevel9k\/powerlevel9k"/' ~/.zshrc

echo "
POWERLEVEL9K_PROMPT_ON_NEWLINE=true
POWERLEVEL9K_PROMPT_ADD_NEWLINE=true
POWERLEVEL9K_LEFT_SEGMENT_SEPARATOR=$'\\\uE0B1'
POWERLEVEL9K_RIGHT_SEGMENT_SEPARATOR=$'\\\uE0B3'
POWERLEVEL9K_MULTILINE_FIRST_PROMPT_PREFIX=\"%{%F{249}%}\\\u250f\"
POWERLEVEL9K_MULTILINE_SECOND_PROMPT_PREFIX=\"%{%F{249}%}\\\u2517%{%F{default}%}❯ \"
POWERLEVEL9K_VCS_STAGED_ICON=\"\\\u00b1\"
POWERLEVEL9K_VCS_UNTRACKED_ICON=\"\\\u25CF\"
POWERLEVEL9K_VCS_UNSTAGED_ICON=\"\\\u00b1\"
POWERLEVEL9K_VCS_INCOMING_CHANGES_ICON=\"\\\u2193\"
POWERLEVEL9K_VCS_OUTGOING_CHANGES_ICON=\"\\\u2191\"
POWERLEVEL9K_VCS_CLEAN_FOREGROUND='green'
POWERLEVEL9K_VCS_CLEAN_BACKGROUND='clear'
POWERLEVEL9K_VCS_MODIFIED_BACKGROUND=\"clear\"
POWERLEVEL9K_VCS_UNTRACKED_BACKGROUND=\"clear\"
POWERLEVEL9K_VCS_MODIFIED_FOREGROUND=\"yellow\"
POWERLEVEL9K_VCS_UNTRACKED_FOREGROUND=\"yellow\"
POWERLEVEL9K_DIR_HOME_BACKGROUND=\"clear\"
POWERLEVEL9K_DIR_HOME_FOREGROUND=\"blue\"
POWERLEVEL9K_DIR_HOME_SUBFOLDER_BACKGROUND=\"clear\"
POWERLEVEL9K_DIR_HOME_SUBFOLDER_FOREGROUND=\"blue\"
POWERLEVEL9K_DIR_DEFAULT_BACKGROUND=\"clear\"
POWERLEVEL9K_DIR_DEFAULT_FOREGROUND=\"white\"
POWERLEVEL9K_ROOT_INDICATOR_BACKGROUND=\"red\"
POWERLEVEL9K_ROOT_INDICATOR_FOREGROUND=\"white\"
POWERLEVEL9K_TODO_BACKGROUND=\"clear\"
POWERLEVEL9K_TODO_FOREGROUND=\"green\"
POWERLEVEL9K_OS_ICON_BACKGROUND=\"clear\"
POWERLEVEL9K_OS_ICON_FOREGROUND=\"white\"
POWERLEVEL9K_HISTORY_BACKGROUND=\"clear\"
POWERLEVEL9K_HISTORY_FOREGROUND=\"blue\"
POWERLEVEL9K_STATUS_OK_BACKGROUND=\"clear\"
POWERLEVEL9K_STATUS_OK_FOREGROUND=\"green\"
POWERLEVEL9K_STATUS_ERROR_BACKGROUND=\"clear\"
POWERLEVEL9K_STATUS_ERROR_FOREGROUND=\"red\"
POWERLEVEL9K_LOAD_CRITICAL_BACKGROUND=\"clear\"
POWERLEVEL9K_LOAD_WARNING_BACKGROUND=\"clear\"
POWERLEVEL9K_LOAD_NORMAL_BACKGROUND=\"clear\"
POWERLEVEL9K_LOAD_CRITICAL_FOREGROUND=\"red\"
POWERLEVEL9K_LOAD_WARNING_FOREGROUND=\"yellow\"
POWERLEVEL9K_LOAD_NORMAL_FOREGROUND=\"green\"
POWERLEVEL9K_LOAD_CRITICAL_VISUAL_IDENTIFIER_COLOR=\"red\"
POWERLEVEL9K_LOAD_WARNING_VISUAL_IDENTIFIER_COLOR=\"yellow\"
POWERLEVEL9K_LOAD_NORMAL_VISUAL_IDENTIFIER_COLOR=\"green\"
POWERLEVEL9K_RAM_BACKGROUND=\"clear\"
POWERLEVEL9K_RAM_FOREGROUND=\"green\"
POWERLEVEL9K_RAM_ELEMENTS=\"ram_free\"
POWERLEVEL9K_TIME_BACKGROUND=\"clear\"
POWERLEVEL9K_TIME_FOREGROUND=\"white\"
POWERLEVEL9K_TIME_FORMAT=\"%D{\\\uf017 %H:%M \\\uf073 %d.%m.%y}\"
POWERLEVEL9K_STATUS_VERBOSE=\"true\"
POWERLEVEL9K_LEFT_PROMPT_ELEMENTS=(root_indicator context dir vcs)
POWERLEVEL9K_RIGHT_PROMPT_ELEMENTS=(status background_jobs load ram)
" >> ~/.zshrc

echo "
export DEFAULT_USER=$USER
alias gpp='git push --set-upstream origin \$(git_current_branch)'
" >> ~/.zshrc

echo "
export LANG=fr_FR.UTF-8
export GDM_LANG=fr_FR.utf8
LC_ALL=fr_FR.UTF-8
LC_CTYPE=fr_FR.UTF-8
" >> .zshrc

mkdir ~/.config/terminator
touch ~/.config/terminator/config
echo "
[global_config]
  title_transmit_fg_color = \"#c5c8c6\"
  title_transmit_bg_color = \"#282a2e\"
  title_inactive_fg_color = \"#c5c8c6\"
  title_inactive_bg_color = \"#373b41\"
  title_hide_sizetext = True
  window_state = maximise
  inactive_color_offset = 0.74
[profiles]
  [[default]]
    palette = \"#282a2e:#a54242:#8c9440:#de935f:#5f819d:#85678f:#5e8d87:#707880:#373b41:#cc6666:#b5bd68:#f0c674:#81a2be:#b294bb:#8abeb7:#c5c8c6\"
    foreground_color = \"#c5c8c6\"
    background_color = \"#1d1f21\"
    cursor_color = \"#c5c8c6\"
 
[layouts]
  [[default]]
    [[[child1]]]
      type = Terminal
      parent = window0
      profile = default
    [[[window0]]]
      type = Window
      parent = \"\"
[plugins]
" > ~/.config/terminator/config

source ~/.zshrc
 
```

## Tools

```bash
sudo apt-get install system-config-printer kid3 \
    vlc xclip htop vim \
    numlockx software-properties-common apt-transport-https
sudo sed -i 's/#greeter-setup-script\=/greeter-setup\-script=\/usr\/bin\/numlockx on/' /etc/lightdm/lightdm.conf

```

## Git setup

```bash
sudo apt-get install kdiff3 git
 
git config --global user.email "contact@gb-prod.fr"
git config --global user.name "Gilles"
git config --global core.editor "vim"
git config --global push.default simple
git config --global merge.tool kdiff3
```

## Theme

```bash
sudo apt-get install faenza-icon-theme arc-theme
```

## Nas

```bash
sudo apt-get install cifs-utils
sudo mkdir /mnt/data
touch ~/.nas_credencials
echo "username=*****" > ~/.nas_credencials
echo "password=*****" >> ~/.nas_credencials
echo "//192.168.0.10/Volume_1 /mnt/data cifs credentials=/home/gilles/.nas_credencials,iocharset=utf8,noperm,auto 0 0" | sudo tee -a /etc/fstab
sudo mount -a
```

## Sublime text

```bash
wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -
echo "deb https://download.sublimetext.com/ apt/stable/" | sudo tee /etc/apt/sources.list.d/sublime-text.list
sudo apt-get update
sudo apt-get install sublime-text
```

## Docker

```bash 
sudo apt-get install \
     apt-transport-https \
     ca-certificates \
     curl \
     gnupg2 \
     software-properties-common
     
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo apt-key add -

sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/debian \
   $(lsb_release -cs) \
   stable"
sudo apt-get update
sudo apt-get install docker-ce
sudo groupadd docker
sudo usermod -aG docker $USER
```

## PHP/Composer

```
echo "
export PHP_VERSION=latest
alias php='docker run -it --rm -w=/www --name=php-cli -v \$(pwd):/www php:\$PHP_VERSION php'
alias composer='docker run -it --rm --user \$(id -u):\$(id -g) --volume /etc/passwd:/etc/passwd:ro --volume /etc/group:/etc/group:ro --volume \$(pwd):/app composer'
export PHP='docker run -it --rm -w=/www --name=php-cli -v \$\$(pwd):/www php:\$\$PHP_VERSION php'
export COMPOSER='docker run -it --rm --user \$\$(id -u):\$\$(id -g) --volume /etc/passwd:/etc/passwd:ro --volume /etc/group:/etc/group:ro --volume \$\$(pwd):/app composer'

" >> ~/.zshrc
