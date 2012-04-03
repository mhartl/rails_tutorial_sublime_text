# Rails Tutorial Sublime Text setup

These are the steps needed to set up [Sublime Text 2](http://www.sublimetext.com/) as in the [Ruby on Rails Tutorial](http://ruby.railstutorial.org). Instructions are for OS X; Linux and Windows users should make substitutions as necessary.

## Basic configuration

`View > Hide Minimap`

`View > Side Bar > Hide Side Bar`

`View > Layout > Columns: 2`

## Copy auxiliary files

    $ cd /tmp
    $ git clone git@github.com:mhartl/rails_tutorial_sublime_text.git
    $ cp -r rails_tutorial_sublime_text/* \
            ~/Library/Application\ Support/Sublime\ Text\ 2/Packages/User/

Setup on Linux should be similar, but with a different target directory for `cp`. If you know how to set it up on Windows, please [let me know](http://railstutorial.org/contact).

## Set up the theme

Select `Preferences > Color Scheme > User > Railscasts`

## Install the Rails Tutorial snippets

[https://github.com/mhartl/rails_tutorial_snippets](https://github.com/mhartl/rails_tutorial_snippets)

## Install Sublime Alternative Auto-completion

[https://github.com/alexstaubo/sublime_text_alternative_autocompletion](https://github.com/alexstaubo/sublime_text_alternative_autocompletion)

## Install SublimeERB

[https://github.com/eddorre/SublimeERB](https://github.com/eddorre/SublimeERB)

## Install RubyTest

Follow [https://github.com/maltize/sublime-text-2-ruby-tests](https://github.com/maltize/sublime-text-2-ruby-tests). Then edit the file `"Theme - Default/Widget.sublime-settings"` in the `Library/Application\ Support/Sublime\ Text\ 2/Packages directory`:
    $ cd ~/Library/Application\ Support/Sublime\ Text\ 2/Packages
    $ subl "Theme - Default/Widget.sublime-settings" 

In that file, change

    "color_scheme": "Packages/Theme - Default/Widgets.stTheme"

to 

    "color_scheme": "Packages/User/CustomTestConsole.tmTheme"

