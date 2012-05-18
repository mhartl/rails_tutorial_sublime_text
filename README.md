# Rails Tutorial Sublime Text setup

These are the steps needed to set up [Sublime Text 2](http://www.sublimetext.com/) as in the [Ruby on Rails Tutorial](http://ruby.railstutorial.org). Instructions are for OS X; Linux and Windows users should make substitutions as necessary. (This may require web searches. Please let me know if you find something that you think should be included here.)

## Command-line command

On OS X, you can set up `subl` as a command-line command by following the [Sublime Text&nbsp;2 instructions for the OS X command line](http://www.sublimetext.com/docs/2/osx_command_line.html):

    $ ln -s "/Applications/Sublime Text 2.app/Contents/SharedSupport/bin/subl" ~/bin/subl

This assumes that `~/bin` is in your path.

For other platforms, either double-click the application icon or search around to learn how to set a command-line command. (Please email me if you figure it out for either Windows or Linux and I'll post the results here.)

## Basic configuration

`View > Hide Minimap`

`View > Side Bar > Hide Side Bar`

`View > Layout > Columns: 2`

## Copy auxiliary files

    $ cd /tmp
    $ git clone git@github.com:mhartl/rails_tutorial_sublime_text.git
    $ cp -r rails_tutorial_sublime_text/* \
            ~/Library/Application\ Support/Sublime\ Text\ 2/Packages/User/

Setup on Linux should be similar, but with a different target directory for `cp`. 

On Windows, the target directory is as follows:

    $ cd /tmp
    $ git clone git@github.com:mhartl/rails_tutorial_sublime_text.git
    $ cp -r .\rails_tutorial_sublime_text\* \
            '~\AppData\Roaming\Sublime Text 2\Packages\User'

## Install Sass syntax highlighting

Follow the instructions at [sublime-text-haml-sass](https://github.com/n00ge/sublime-text-haml-sass).

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

