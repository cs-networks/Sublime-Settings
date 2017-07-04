# Sublime-Settings
I'm working on several different machines, private and business ones. Keeping all my Sublime Text settings in sync was not possible anymore. So I decided to my settings under Version control with a centralized git repository.

> Create the repository
First create the Git repository and get the URL of your new repository. You can directly create a .gitignore file with the following content:

# Ignore everything...
*
# ... except preferences
!.gitignore
!Preferences.sublime-settings
!Package Control.sublime-settings

These files contains all settings and a list of installed packages. If that list has changed and Sublime Text is restarted, Package Control will automatically install missing packages, as described here. It’s even possible to sync modified theme files. You only have to copy them into the user directory, add them to the .gitignore file with exclamation mark and change the path to the theme files in the user settings.

> Set up the first device

First you will have to push your current Sublime Text settings to the remote repository. Therefore you can use the following Git commands, assuming you have created a Git repository a server:

$ git init
$ git remote add origin <repository url>
$ git fetch
$ git commit -am "added: settings and packages"
$ git push

> Set up all other devices

Now you can create the repository in the existing user directory of all other Sublime Text devices:

$ git init
$ git remote add origin <repository url>
$ git fetch
$ git reset --hard origin/master

With the last line, the existing setting files will be overwritten by those from the repository.

## License
This program is distributed under the terms of the GNU GPL v3. See the [LICENSE][license] file for more details.

[license]: https://raw.githubusercontent.com/cs-networks/Sublime-Settings/master/LICENSE
