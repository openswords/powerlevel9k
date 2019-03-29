# Change Note

## PROMPT_ELEMENTS

example: `POWERLEVEL9K_LEFT_PROMPT_ELEMENTS=(ram dir rbenv vcs)`

What that is referred to in the parentheses is defined with `prompt_` concatenated with its name, eg., `prompt_dir()`.

## Change the color of an icon

for example `prompt_ram()`

```
  #"$1_prompt_segment" "$0" "$2" "yellow" "$DEFAULT_COLOR" "$(printSizeHumanReadable "$ramfree" $base)" 'RAM_ICON'
  "$1_prompt_segment" "$0" "$2" "244" "black" "$(printSizeHumanReadable "$ramfree" $base)" 'RAM_ICON'
```

black is the color of the icon, 244 is the background color

## virtualenv

```
prompt_virtualenv() {
  local virtualenv_path="$VIRTUAL_ENV"
  if [[ -n "$virtualenv_path" && "$VIRTUAL_ENV_DISABLE_PROMPT" != true ]]; then
    "$1_prompt_segment" "$0" "$2" "blue" "$DEFAULT_COLOR" "$(basename "$virtualenv_path")" 'PYTHON_ICON'
  fi
}
```

$VIRTUAL_ENV has no value unless virtualenv is activated.

