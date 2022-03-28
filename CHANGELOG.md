# Changelog: rich-click

## Version 1.2.2.dev0

- Added initial support for [Typer](https://typer.tiangolo.com/) [[#26](https://github.com/ewels/rich-click/pull/26)]
- Mark PEP 561 Compatibility [[#41](https://github.com/ewels/rich-click/pull/41)]
- Distribution now available via MacPorts [[#42](https://github.com/ewels/rich-click/pull/42)]
- Add typing information [[#39](https://github.com/ewels/rich-click/pull/39)]
- Refactor `RichCommand` and `RichGroup` out of `rich_click` [[#38](https://github.com/ewels/rich-click/pull/39)]
- Change metavar overflow to `fold`, so that large numbers of choices flow onto new lines instead of being truncated with an ellipsis [[#33](https://github.com/ewels/rich-click/issues/33)]
- Make metavar separators dim (`[]`,`<>`) (customise with `STYLE_METAVAR_SEPARATOR`)
- Add pre-commit config and a lot more linters (iSort, mypy, Flake8) [[#40](https://github.com/ewels/rich-click/pull/40)]
- Monkey-patch `RichCommand` and `RichGroup` in CLI code for better `rich-click` compatability with more tools [[#43](https://github.com/ewels/rich-click/pull/43)]
- Parse emoji shortcodes `:partying_face:` [[#51](https://github.com/ewels/rich-click/pull/51)]
- Pushed minimum version of Python up to 3.7, in line with [Click v8.1](https://click.palletsprojects.com/en/8.1.x/changes/#version-8-1-0)
- Fixed bug where `--no-myflag` wasn't showing in the help [[#45](https://github.com/ewels/rich-click/issues/45)]

## Version 1.2.1 (2022-03-02)

- Support the command `short_help` argument [[#28](https://github.com/ewels/rich-click/issues/28)]
- Added `USE_CLICK_SHORT_HELP` global to enable default click shortening of help messages [[#28](https://github.com/ewels/rich-click/issues/28)]
- Avoid `AttributeError` exceptions when using custom exception classes based on click that don't have `ctx` [[#27](https://github.com/ewels/rich-click/issues/27)]
- Fix bug in inverted secondary options [[#31](https://github.com/ewels/rich-click/issues/31)]
- Refactor printing options to handle arbitrary numbers of flags [[#32](https://github.com/ewels/rich-click/issues/32)]

## Version 1.2.0 (2022-02-28)

- New CLI functionality to richifiy via prefix any other tool using click, by @pawamoy [[#13](https://github.com/ewels/rich-click/pull/13)]
- Distribution now available via conda-forge

## Version 1.1.1 (2022-02-28)

Hotfix patch release to remove an accidental `from turtle import st` that crept in due to a pesky VSCode plugin.
Many thanks to [@ashb](httpsd://github.com/ashb) for spotting.

## Version 1.1.0 (2022-02-28)

- Added support for `HEADER_TEXT` and `FOOTER_TEXT` to go before and after help output
- Catch Abort exceptions from `cmd+c` and print nicely using `ABORTED_TEXT`
- Handle missing `click.types._NumberRangeBase` in click 7x [[#16](https://github.com/ewels/rich-click/issues/16)]
- Fix compatibility issue for rich 10.6 (`group` vs `render_group` import) [[#16](https://github.com/ewels/rich-click/issues/16)]
- Require at least click v7.0 (released 2018) [[#16](https://github.com/ewels/rich-click/issues/16)]
- Require at least rich v10 (released March 2021) [[#16](https://github.com/ewels/rich-click/issues/16)]
- Unwrap single newlines in option and group-command help texts [[#23](https://github.com/ewels/rich-click/issues/23)]
- Add click `\b` escape marker functionality into help text rendering [[#24](https://github.com/ewels/rich-click/issues/24)]
- Fix syntax in example in README file by @fridex [[#15](https://github.com/ewels/rich-click/pull/15)]

## Version 1.0.0 (2022-02-18)

- _**Major change:**_ New usage, so that we can avoid having to do monkey patching [[#10](https://github.com/ewels/rich-click/pull/10).]
  - Now use with `import rich_click as click`
- Add ability to create groups of options with separate panels
- Show positional arguments in their own panel by default
- Add config `GROUP_ARGUMENTS_OPTIONS` option to group with options
- Improve handing of metavars, give option to show appended instead of in column
- Add `COLOR_SYSTEM` option to add ability to disable colours
- Add options to customise error message help texts
- Add support for printing errors nicely
- A lot of additional testing and tweaking

## Version 0.3.0 (2022-02-13)

- Add ability to create groups of commands with separate panels
- Add support for rich console markup or Markdown in help texts
- Set default for `MAX_WIDTH` to `None` instead of `100`
- Switch boolean option `SKIP_ARGUMENTS` to `SHOW_ARGUMENTS`
- Improve regular expression for flags like `-bg`
- Use click's string for default value, instead of the value directly
- Show some previously missed metavar types (eg. choice and range options)
- Stripped required-asterisk column from options table if none are required

## Version 0.2.0 (2022-02-10)

- Made most styling decisions configurable
- Added support for more click parameters
  - Showing default values, showing if required, showing if deprecated, epilog
  - Option now hidden if set in click

## Version 0.1.2 (2022-02-10)

- Seems to work fine on Python 3.6, so dropped the requirement down to this instead of Python 3.7

## Version 0.1.1 (2022-02-10)

- Fix a bug in `setup.cfg` that broke installation

## Version 0.1.0 (2022-02-09)

Initial development version of `rich-click`, mostly as a proof of concept.

Supports basic generic functionality for printing help from click commands and groups.

Code was initially written by [@willmcgugan](https://github.com/willmcgugan) for `rich-cli`
and then further developed by [@ewels](http://github.com/ewels/).
