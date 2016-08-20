# Terminal

## Oh-my-zsh

```bash
sudo apt-get install curl git vim zsh
chsh -s $(which zsh)
```

Fermer et ouvrir la session

```
curl -L http://install.ohmyz.sh | sh
sed -i 's/^ZSH_THEME=.*/ZSH_THEME="agnoster"/' ~/.zshrc
sed -i 's/^plugins=.*/plugins=(git bower composer debian nyan sublime symfony2 docker taskwarrior)/' ~/.zshrc
source ~/.zshrc
 
wget https://github.com/Lokaltog/powerline/raw/develop/font/PowerlineSymbols.otf https://github.com/Lokaltog/powerline/raw/develop/font/10-powerline-symbols.conf
sudo mv PowerlineSymbols.otf /usr/share/fonts/
sudo fc-cache -vf
sudo mv 10-powerline-symbols.conf /etc/fonts/conf.d/
```

## Configuration de terminator

```bash
sudo apt-get install terminator
```

Dans préférence
 * Décocher windows borders
 * Window state : maximized
 * Cocher Hide size from title
 * Dans Focused terminal / Background color : #008000
 * Dans Profiles / Background : Choir Transparent Background 0,8
 * Dans Profiles / Colors : White on Black et Ambiance
 
Ou en modifiant le fichier de configuration!
```
[global_config]
  title_transmit_fg_color = "#c5c8c6"
  title_transmit_bg_color = "#282a2e"
  title_inactive_fg_color = "#c5c8c6"
  title_inactive_bg_color = "#373b41"
  title_hide_sizetext = True
  window_state = maximise
  inactive_color_offset = 0.74
[profiles]
  [[default]]
    palette = "#282a2e:#a54242:#8c9440:#de935f:#5f819d:#85678f:#5e8d87:#707880:#373b41:#cc6666:#b5bd68:#f0c674:#81a2be:#b294bb:#8abeb7:#c5c8c6"
    foreground_color = "#c5c8c6"
    background_color = "#1d1f21"
    cursor_color = "#c5c8c6"
 
[layouts]
  [[default]]
    [[[child1]]]
      type = Terminal
      parent = window0
      profile = default
    [[[window0]]]
      type = Window
      parent = ""
[plugins]
```
