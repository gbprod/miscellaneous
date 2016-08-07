```bash
sudo add-apt-repository ppa:webupd8team/atom
sudo apt-get update
sudo apt-get install atom

apm install railscast-theme autocomplete-php install atom-autocomplete-php
```

**config.cson**
```cson
"*":
  "atom-autocomplete-php":
    binComposer: "composer"
    insertNewlinesForUseStatements: true
  "autocomplete-php": {}
  core:
    themes: [
      "one-dark-ui"
      "railscast-theme"
    ]
  editor:
    scrollPastEnd: true
  welcome:
    showOnStartup: false
```

