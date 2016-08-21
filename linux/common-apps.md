# Applications diverses

```bash
sudo apt-get install \
    chromium-browser kid3 \
    vlc chromium-browser-l10n task xclip htop vim \
    fonts-inconsolata numlockx
```

### Num lock on startup
```bash
sudo sed -i '/#\!\/bin\/sh/a if [ -x /usr/bin/numlockx ]; then \
/usr/bin/numlockx on \
fi' /etc/mdm/Init/Default
```
