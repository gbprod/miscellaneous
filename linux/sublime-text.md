# Sublime Text

## Plugins

  * Railscast color scheme
  * Maybs Quit
  * SideBarEnhancements
  * Php Companion
  * DocBlockr
  * All autocomplete
  * Alignment
  * Case Conversion
  * TabsExtra
  * MarkdownEditing
  * Afterglow

## Configuration

### Keymap

```javascript
[
    { "keys": ["ctrl+tab"], "command": "next_view" },
    { "keys": ["ctrl+shift+tab"], "command": "prev_view" },
    { "keys": ["f12"], "command": "goto_definition" },
    { "keys": ["ctrl+pagedown"], "command": "next_view_in_stack" },
    { "keys": ["ctrl+,"], "command": "show_overlay", "args": {"overlay": "goto", "text": "#"} },
    { "keys": ["ctrl+space"], "command": "auto_complete" },
    { "keys": ["ctrl+;"], "command": "run_macro_file", "args": {"file": "Packages/User/eol_semi.sublime-macro"} },
    { "keys": ["ctrl+pageup"], "command": "prev_view_in_stack" }
]
```

### Settings

```javascript
{
	"color_scheme": "Packages/RailsCasts Colour Scheme/RailsCastsColorScheme.tmTheme",
	"ensure_newline_at_eof_on_save": true,
	"tabs_small": true,
	"status_bar_brighter": true,
	"tabs_padding_medium": true,
	"font_size": 10,
	"highlight_line": true,
	"highlight_modified_tabs": true,
	"ignored_packages":
	[
		"Vintage",
		"Markdown"
	],
	"line_padding_top": 1,
	"rulers":
	[
		80,
		120
	],
	"show_encoding": true,
	"tab_completion": false,
	"theme": "Afterglow-orange.sublime-theme",
	"translate_tabs_to_spaces": true,
	"trim_trailing_white_space_on_save": true,
	"word_wrap": "false"
}
```

### DocBlockr configuration

```javascript
{
  "jsdocs_return_description": false,
  "jsdocs_param_description": false,
  "jsdocs_spacer_between_sections": true,
  "jsdocs_per_section_indent": true,
  "jsdocs_short_primitives": true
}
```

### Markdown GFM configuration

```javascript
{
    "color_scheme": "Packages/MarkdownEditing/MarkdownEditor-Dark.tmTheme",
    "draw_centered": false,
    "word_wrap": false,
    "line_numbers": true,
    "caret_style": "solid",
    "caret_extra_width": 1
}
```

## Macros

`Packages/User/eol_semi.sublime-macro`
```javascript
[
    {"command": "move_to", "args": {"to": "eol", "extend": false} },
    {"command": "trim_trailing_white_space"},
    {"command": "insert", "args": {"characters": ";"}}
]
```

**getter**
```xml
<snippet>
    <content><![CDATA[/**
 * Getter for ${1:$SELECTION}
 *
 * @return ${2:$SELECTION}
 */
public function get${1/(?:^|_)(\w)/\U$1$2/g$1}()
{
    return \$this->$1;
}
]]></content>
    <!-- Optional: Tab trigger to activate the snippet -->
    <tabTrigger>getter</tabTrigger>
    <!-- Optional: Scope the tab trigger will be active in -->
    <scope>source.php</scope>
    <!-- Optional: Description to show in the menu -->
    <description>Create getter method</description>
</snippet>
```

`author.sublime-snippet`
```xml
<snippet>
    <content><![CDATA[
@author GBProd <contact@gb-prod.fr>
]]></content>
    <tabTrigger>auth</tabTrigger>
</snippet>
```
 
