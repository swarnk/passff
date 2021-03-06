passff
======

[![Join the chat at https://gitter.im/jvenant/passff](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/jvenant/passff?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

**[zx2c4 pass](http://www.zx2c4.com/projects/password-store/)** management extension for Firefox, Chrome\*, and Opera\*

**Official signed version can be found on the [Mozilla add-on page](https://addons.mozilla.org/firefox/addon/passff)**

![passff](https://user-images.githubusercontent.com/1518387/33810636-8c95df16-de07-11e7-8857-283e7300ecff.png)

### Overview
This extension will allow you to access your **[zx2c4 pass](http://www.zx2c4.com/projects/password-store/)** repository directly from your web browser.

You can choose to automatically fill and submit login forms if a matching password entry is found.

### Installation
- You need **[zx2c4 pass](http://www.zx2c4.com/projects/password-store/)** installed on your computer and a password respository with [password files configured to our format](#password-configuration)
- You will also need to **[install the host application](docs/INSTALLATION.md#installing-the-host-application)** so the extension can communicate with `pass` to retrieve your passwords
- Install the current release for your browser:
  - [Firefox](https://addons.mozilla.org/firefox/addon/passff)
  - Chrome, Chromium (coming soon)
  - Vivaldi, Opera (coming soon)

Alternatively, you can install an older version or the latest build from GitHub by refering to [instructions here](docs/INSTALLATION.md).

##### Password configuration
If you only want the extension to fill out passwords, you don't need any special format for your password files. But if you follow our format, the extension can also visit the website's URL and fill out the username and other input fields for you.

The format is:
```
<the_password>
login: <the_login>
url: <the_url>
<other_inputfield_name> : <inputfield_value>
```

You can change or configure additional names for the login and url values in preferences.

Lines besides the login and URL that match the format `<other_inputfield_name>: <value>` can be used to fill in input fields besides the login and password fields. The left hand side of the colon should match the input field's `name` or `id` attribute.

Alternatively, you can organize your login information with file structure. For example, if you have this file structure:
* www
  * supersite.com
    * login
    * user
  * mysite.com

PassFF will
* get the login from the "login" file under supersite.com
* get the login from the "login" field inside the mysite.com entry for mysite.com (see format above)

The file structure approach does not support custom input fields, however.

### Usage
Once installed, you should have a new icon in your toolbar. Click the icon to browse your password repository or search using a **fuzzy matching** algorithm.

##### Keyboard shortcuts
The default shortcut to open the menu is <kbd>ctrl</kbd>+<kbd>y</kbd>.

With the menu open, you can press <kbd>enter</kbd> to execute one of the following commands, according to your preferences:
- Fill and submit
- Goto, fill and submit
- Copy login to clipboard
- Copy password to clipboard

##### Preferences
From the extension preferences you will be able to set:
- Inputs (A comma separated list of input names. Input field names in a html page containing one of those values will be filled with the corresponding value.)
  - Passwords input names
  - Login input names
- Fields (A comma separated list of field names. The first matching field in the password data or in the store tree will be used as the corresponding value.)
  - Login field names
  - Password field names
  - URL field names
- Adding Passwords
  - The default length for generating passwords
  - Whether or not to include symbols in generated passwords by default
  - Preferred new password method ("generate" or "insert")

### Issues
If you're having problems, the most common causes are misconfigured preferences or an improperly installation of the host application. You can get more information by [debugging the extension](docs/CONTRIBUTING.md).

First, [make sure the host application is installed correctly](docs/INSTALLATION.md#installing-the-host-application).

Configure the script's execution parameters appropriately in the host app `passff.py`: E.g., set `command` to the path to the `pass` binary (if installed with homebrew, the default location is `/usr/local/bin/pass`). With those settings in place, the extension should be able to find your passwords.

### Thanks
Development and improvements
 * [Johan Venant](https://github.com/jvenant)
 * [Tobias Umbach](https://github.com/sometoby)
 * [Lenz Weber](https://github.com/phryneas)
 * [Thomas Vogt](https://github.com/tuxor1337)

Russian translation : [Grigorii Horos](https://github.com/horosgrisa)
