```bash
sudo add-apt-repository ppa:webupd8team/atom
sudo apt-get update
sudo apt-get install atom

apm install railscast-theme autocomplete-php install atom-autocomplete-php goto-definition
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
    tabLength: 4
  welcome:
    showOnStartup: false
```

**snippets.cson**
```cson
'*':
  'author':
    'prefix': 'author'
    'body': '@author gbprod <contact@gb-prod.fr>'
```

**keymap.cson**
```cson
'.platform-linux atom-text-editor:not(.mini)':
  'F12': 'goto-definition:go'
```
