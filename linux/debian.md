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

git clone https://github.com/gabrielelana/awesome-terminal-fonts.git
mkdir ~/.fonts
mv awesome-terminal-fonts/build/* ~/.fonts
fc-cache -fv ~/.fonts
mkdir -p ~/.config/fontconfig/conf.d
mv awesome-terminal-fonts/config/10-symbols.conf ~/.config/fontconfig/conf.d
sed -i 's/<family>PragmataPro<\/family>/<family>FontAwesome<\/family>/' ~/.config/fontconfig/conf.d/10-symbols.conf
echo "source ~/.fonts/*.sh" >> ~/.zshrc 

echo "POWERLEVEL9K_MODE='awesome-fontconfig'
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



source ~/.zshrc
 
```
