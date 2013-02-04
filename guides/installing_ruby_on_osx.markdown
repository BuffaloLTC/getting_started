# Install Ruby on OSX

Thanks to the open-source community, installing Ruby on OSX is a breeze. These
instructions will walk you through the process of installing the latest version
of Ruby so that you can begin coding right away!

We'll be using the command line quite a bit. If this sounds intimidating, check
out our [command line primer](https://github.com/BuffaloLTC/getting_started/wiki/Command-Line-primer)
beforehand.

## Installing a "C" Compiler

Before we can install any other tools, we'll need a compiler to create them.
[Xcode](https://developer.apple.com/xcode/) is Apple's development environment
for OSX and iOS and includes the LLVM C compiler (Ruby is written in C). If you
want the full Xcode, it can be easily installed through the
[App Store](https://itunes.apple.com/us/app/xcode/id497799835?ls=1&mt=12).

For Ruby, however, we can alternatively install only the command-line tools,
which are hidden in Apple's obscure
[developer portal](https://developer.apple.com/downloads/). Visit the link, and
if needed, create an Apple ID (it's free). From the list of downloads, find the
Command Line Tools...

![Finding the command-line tools in the Apple Developer Portal](https://raw.github.com/BuffaloLTC/getting_started/master/images/command_line_tools_dropdown.jpg)

...click the icon to download, find the package on your Mac (likely the
`~/Downloads` directory), and double-click to install.

## Installing a Package Manager

Working with Ruby and the command-line is greatly streamlined through the use
of a package manager. A package manager handles all of the hard work of keeping
programs (packages) up-to-date, insuring they have all of the needed files
(dependancies), and installing the programs (compiling the packages from the
source code) onto your computer. In fact, the App Store is a sort of package
manager, though not free or open-source.

Our package manager of choice is [Homebrew](http://mxcl.github.com/homebrew/).
To install, read through the [Homebrew introduction](http://mxcl.github.com/homebrew/)
for a quick overview of Homebrew, and then follow the instructions listed under
"Install Homebrew" at the bottom of the page.

![How to install Homebrew.](https://raw.github.com/BuffaloLTC/getting_started/master/images/homebrew_installation.jpg)

If you haven't yet, open a new Terminal window, paste in the command from the
[Homebrew instructions](http://mxcl.github.com/homebrew/), and follow the
printed instructions. You now have a package manager with access to thousands
of open-source command-line tools. Type `brew` into the Terminal for an idea of
what can be done with this package manager.

## Installing Version Control

Though not strictly necessary for programming, it's generally considered a bad
idea to program without some sort of version control. If you're not certain
what that is, check out CodeSchool's [Git primer](http://try.github.com/)
beforehand.

With our newfound package manager, installing Git is a breeze. Simply enter
`brew install git` into the Terminal and watch as it compiles. After completion,
enter `git` into the terminal for list of the most often-used Git commands.

## Installing Ruby

Finally, we're ready to install Ruby... almost. Ruby exists in many versions;
the version is indicated by three numbers separated by periods. To see the
current version, visit the [official Ruby site](http://www.ruby-lang.org/en/).
At the time of writing, 1.9.3-p374 is the latest Ruby version. Once a project
is begun in a particular version, you'll rarely want to change it without
extensive testing to ensure your program behaves the save. For this reason, it
is common to use a version manager to automatically switch between Rubies
depending on the current project.

Our version manager of choice is [Rbenv](https://github.com/sstephenson/rbenv)
(short for RuBy ENVironment). To install Rbenv, enter `brew install rbenv
ruby-build` into the Terminal. These two tools, combined, make installing and
managing Ruby versions a breeze. For a list of Rbenv's most useful commands,
enter 'rbenv' and 'ruby-build' into the Terminal.

We're not done yet, though. Rbenv requires
[some special attention](https://github.com/sstephenson/rbenv#installation)
from us to function properly. Follow
[Rbenv installation instructions](https://github.com/sstephenson/rbenv#installation)
1-4 to ensure Rbenv can be accessed by the system.

Now, we can install Ruby! First, enter `ruby-build --definitions` into the
terminal for a list of the supported Ruby versions. Currently, we want the
latest patch-level release of Ruby 1.9.3, which the ruby-build says is
1.9.3-p374. To install, then, enter into the Terminal `rbenv install
1.9.3-p374`. Ruby has begun installing!

Once complete, we need to make sure Rbenv knows about our install. To do so,
enter `rbenv rehash` into the Terminal. Once complete, enter `rbenv versions`;
we should see our version of Ruby listed. We want to make this version of Ruby
available to the entire system, so that the much-older version of Ruby packaged
with OSX isn't invoked. To do so, enter `rbenv global 1.9.3-p374` into the
Terminal. This version of Ruby should now be available to the entire system. To
test, enter `ruby --version` into the Terminal. If the version displayed matches
the version installed, congratulations— you now have the latest version of Ruby 
installed on your Mac.
