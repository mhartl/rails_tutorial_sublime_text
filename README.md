# Rails Tutorial Sublime Text setup

These are the steps needed to set up [Sublime Text 2](http://www.sublimetext.com/) as in the [Ruby on Rails Tutorial](http://ruby.railstutorial.org). Instructions are for OS X; Linux and Windows users should make substitutions as necessary. (This may require web searches. Please let me know if you find something that you think should be included here.)

## Command-line command

On OS X, you can set up `subl` as a command-line command like this:

    $ ln -s "/Applications/Sublime Text 2.app/Contents/SharedSupport/bin/subl" ~/bin/subl

This assumes that there is a `~/bin` directory on your executable path. If that isn't the case, follow the instructions on [this Stack Overflow thread](http://stackoverflow.com/questions/13655343/sublime-text-2-os-x-command-line).

On Linux (especially Ubuntu), the command is similar to OS X; the paths differ and you must use `sudo`, which is required because ordinary users don't have permission to write to `/usr/bin`:

    $ sudo ln -s ~/Applications/Sublime\ Text\ 2/sublime_text /usr/bin/subl

Alternatively, add an alias to `sumblime_text` in your `~/.bashrc` file.  This method doesn't require `sudo`. But it assumes you are using `bash`. There are similar methods available for other shells. Google is your friend.

Use any editor like gedit or vim to open `~/.bashrc`.
    
    $ gedit ~/.bashrc
    
Add `alias subl='~/Applications/Sublime\ Text\ 2/sublime_text'` at the end of the file. Save and exit.

(You may have to replace the path to `sublime_text` with the correct one for your system.)

On Linux Mint, take a look at [Install Sublime Text 2 in Linux Mint](http://blog.hugeaim.com/2012/03/13/install-sublime-text-2-in-linux-mint/).

On Windows, you can simply double-click the application icon. The setup at the command line depends on which shell you use; see if one of the techinques at the [Stack Overflow discussion on Sublime Text from Command Line (Win7)](http://stackoverflow.com/questions/9440639/sublime-text-from-command-line-win7) works for you. You might also want to check out the video [Easily Open Files from Windows Command Prompt with Sublime Text 2](http://youtu.be/zcUpdw5_uSY) (I suggest changing `st2` to `subl` to be consistent with the instructions for the other platforms).

## Basic configuration

Open up Sublime Text and use the `View` menu to modify the following settings:

`View > Hide Minimap`

`View > Side Bar > Hide Side Bar`

`View > Layout > Columns: 2`

## Copy auxiliary files

    $ cd /tmp
    $ git clone https://github.com/mhartl/rails_tutorial_sublime_text.git
    $ cp -r rails_tutorial_sublime_text/* \
            ~/Library/Application\ Support/Sublime\ Text\ 2/Packages/User/

Setup on Linux is similar, but with a different target directory for `cp`:

    $ cp -r rails_tutorial_sublime_text/* \
            ~/.config/sublime-text-2/Packages/User/

On Windows, the target directory is as follows:

    $ cd /tmp
    $ git clone https://github.com/mhartl/rails_tutorial_sublime_text.git
    $ cp -r .\rails_tutorial_sublime_text\* \
            '~\AppData\Roaming\Sublime Text 2\Packages\User'

Note: If using Windows Vista, 7, or 8, you should first copy all the folders and files from the remote repo into your local temporary folder located at `C:\Users\User\AppData\Local\Temp`. Then proceed to move these same files to `C:\Users\User\AppData\Roaming\Sublime Text 2\Packages\User`.

## Install Sass syntax highlighting

Follow the instructions at [sublime-text-haml-sass](https://github.com/n00ge/sublime-text-haml-sass).

## Set up the theme

Select `Preferences > Color Scheme > User > Railscasts`

## Install the Rails Tutorial snippets

[https://github.com/mhartl/rails_tutorial_snippets](https://github.com/mhartl/rails_tutorial_snippets)

## Install Sublime Text Alternative Auto-completion

[https://github.com/alexstaubo/sublime_text_alternative_autocompletion](https://github.com/alexstaubo/sublime_text_alternative_autocompletion)

## Install SublimeERB

[https://github.com/eddorre/SublimeERB](https://github.com/eddorre/SublimeERB)

## Install RubyTest

Follow [https://github.com/maltize/sublime-text-2-ruby-tests](https://github.com/maltize/sublime-text-2-ruby-tests).

Then edit the file `"TestConsole.hidden-tmTheme"` in the `Library/Application\ Support/Sublime\ Text\ 2/Packages` directory:

    $ cd ~/Library/Application\ Support/Sublime\ Text\ 2/Packages/RubyTest
    $ subl TestConsole.hidden-tmTheme

In that file, change

    <string>#FF1493</string>

to

    <string>#FF0000</string>

If you ever get the error

    /bin/sh: rspec: command not found

you can simply quit Sublime Text and then restart it by typing

    $ subl

(with no dot). If you are using [RVM](http://rvm.io), you can prevent the problem from recurring by running

    $ subl RubyTest.sublime-settings

and changing

      "check_for_rvm": false,

to

      "check_for_rvm": true,

