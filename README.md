# pac-menu
A simple (unofficial) bash client for [repology.org](https://repology.org/) to
quickly check the packaging status of a package among differnt distributions of
GNU/Linux or other supported repositories of repology.

<p align="center">
  <img src="docs/screencast.gif">
</p>

## Dependencies
- `jq fq curl notify-send xdg-open`
- `dmenu | rofi | fuzzel` : only one is needed

In a Debian-like distro, these can be installed with:

``` shell
sudo apt install jq fq curl libnotify-bin dmenu # or rofi/fuzzel
```

## Usage
Check `pac-menu -h`:

```console
Display packaging status in different repositories via repology.org

Usage: pac-menu [OPTIONS] PACKAGE-NAME
Options:
    -d : Use selector menu to enter package-name
    -V : Print version
    -h : Print help message
```

## Examples
- `pac-menu thunar`
- `pac-menu -d`: (then type query in dmenu)
- `pac-menu ripgr`: this would invoke a API search, then a "refine query" step
                    would be shown before proceeding to showing final results

Call with `-d` on invoking via keybinding. A [desktop
file](contrib/repology.desktop) is provided.

## Customization
On top of the script, these variables can be edited:
- `selector_app` : depending on Xorg (dmenu) or Wayland (rofi/fuzzel) 
- `priority_repo` : distro name that you want its status shown first
- `selector_font`
- `use_custom_redirection` : use predefined project urls instead of repology

## Development
- linter: `shellcheck`
- formatter: `shfmt -i 4 -bn -ci -sr`

