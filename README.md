![](https://raw.githubusercontent.com/bhilburn/powerlevel9k-logo/master/logo-banner.png)
---
[![Build Status](https://travis-ci.org/bhilburn/powerlevel9k.svg?branch=master)](https://travis-ci.org/bhilburn/powerlevel9k)
[![Join the chat at https://gitter.im/bhilburn/powerlevel9k](https://badges.gitter.im/bhilburn/powerlevel9k.svg)](https://gitter.im/bhilburn/powerlevel9k?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

Powerlevel9k is a theme for ZSH which uses [Powerline
Fonts](https://github.com/powerline/fonts). It can be used with vanilla ZSH or
ZSH frameworks such as [Oh-My-Zsh](https://github.com/robbyrussell/oh-my-zsh),
[Prezto](https://github.com/sorin-ionescu/prezto),
[Antigen](https://github.com/zsh-users/antigen), and [many
others](https://github.com/bhilburn/powerlevel9k/wiki/Install-Instructions).

Get more out of your terminal. Be a badass. Impress everyone in 'Screenshot Your
Desktop' threads. Use powerlevel9k.

![](http://bhilburn.org/content/images/2015/01/pl9k-improved.png)

You can check out some other users' configurations in our wiki: [Show Off Your
Config](https://github.com/bhilburn/powerlevel9k/wiki/Show-Off-Your-Config).

There are a number of Powerline ZSH themes available, now. The developers of
this theme focus on four primary goals:

1. Give users a great out-of-the-box configuration with no additional
   configuration required.
2. Make customization easy for users who do want to tweak their prompt.
3. Provide useful segments that you can enable to make your prompt even more
   effective and helpful. We have prompt segments for everything from unit test
   coverage to your AWS instance.
4. Optimize the code for execution speed as much as possible. A snappy terminal
   is a happy terminal.

Powerlevel9k can be used to create both very useful and beautiful terminal environments:

![](https://camo.githubusercontent.com/b5d7eb49a30bfe6bdb5706fa3c9be95fe8e5956e/687474703a2f2f67696679752e636f6d2f696d616765732f70396b6e65772e676966)

### Table of Contents

1. [Installation](#installation)
2. [Customization](#prompt-customization)
    1. [Stylizing Your Prompt](https://github.com/bhilburn/powerlevel9k/wiki/Stylizing-Your-Prompt)
    2. [Customizing Prompt Segments](#customizing-prompt-segments)
    3. [Available Prompt Segments](#available-prompt-segments)
3. [Troubleshooting](https://github.com/bhilburn/powerlevel9k/wiki/Troubleshooting)

Be sure to also [check out the Wiki](https://github.com/bhilburn/powerlevel9k/wiki)!

### Installation
There are two installation steps to go from a vanilla terminal to a PL9k
terminal. Once you are done, you can optionally customize your prompt.

[Installation Instructions](https://github.com/bhilburn/powerlevel9k/wiki/Install-Instructions)

1. [Install the Powerlevel9k Theme](https://github.com/bhilburn/powerlevel9k/wiki/Install-Instructions#step-1-install-powerlevel9k)
2. [Install Powerline Fonts](https://github.com/bhilburn/powerlevel9k/wiki/Install-Instructions#step-2-install-a-powerline-font)

No configuration is necessary post-installation if you like the default
settings, but there are plenty of segment customization options available if you
are interested.

### Prompt Customization

Be sure to check out the wiki page on the additional prompt customization
options, including color and icon settings: [Stylizing Your Prompt](https://github.com/bhilburn/powerlevel9k/wiki/Stylizing-Your-Prompt)

#### Customizing Prompt Segments
Customizing your prompt is easy! Select the segments you want to have displayed,
and then assign them to either the left or right prompt by adding the following
variables to your `~/.zshrc`.

| Variable | Default Value | Description |
|----------|---------------|-------------|
|`P9K_LEFT_PROMPT_ELEMENTS`|`(context dir vcs)`|Segment list for left prompt|
|`P9K_RIGHT_PROMPT_ELEMENTS`|`(status root_indicator background_jobs history time)`|Segment list for right prompt|


The table above shows the default values, so if you wanted to set these
variables manually, you would put the following in
your `~/.zshrc`:
```zsh
P9K_LEFT_PROMPT_ELEMENTS=(context dir vcs)
P9K_RIGHT_PROMPT_ELEMENTS=(status root_indicator background_jobs history time)
```
#### Available Prompt Segments
The segments that are currently available are:

**System Status Segments:**
* [`background_jobs`](segments/background_jobs/README.md) - Indicator for background jobs.
* [`battery`](segments/battery/README.md) - Current battery status.
* [`date`](#date) - System date.
* [`dir`](#dir) - Your current working directory.
* [`context`](segments/context/README.md) - Your username and host, conditionalized based on $USER and SSH status.
* `dir_writable` - Displays a lock icon, if you do not have write permissions on the current folder.
* [`disk_usage`](#disk_usage) - Disk usage of your current partition.
* `history` - The command number for the current line.
* [`host`](segments/host/README.md) - Your current host name
* [`ip`](segments/ip/README.md) - Shows the current IP address.
* [`vpn_ip`](segments/vpn_ip/README.md) - Shows the current VPN IP address.
* [`public_ip`](segments/public_ip/README.md) - Shows your public IP address.
* [`load`](segments/load/README.md) - Your machine's load averages.
* `os_icon` - Display a nice little icon, depending on your operating system.
* `ram` - Show free RAM.
* `root_indicator` - An indicator if the user has superuser status.
* [`status`](segments/status/README.md) - The return code of the previous command.
* `swap` - Prints the current swap size.
* [`time`](segments/time/README.md) - System time.
* [`user`](segments/user/README.md) - Your current username
* [`vi_mode`](segments/vi_mode/README.md)- Your prompt's Vi editing mode (NORMAL|INSERT).
* `ssh` - Indicates whether or not you are in an SSH session.

**Development Environment Segments:**
* [`vcs`](#vcs) - Information about this `git` or `hg` repository (if you are in one).

**Language Segments:**
* **GoLang Segments:**
    * `go_version` - Show the current GO version.
* **Javascript / Node.js Segments:**
    * `node_version` - Show the version number of the installed Node.js.
    * `nodeenv` - [nodeenv](https://github.com/ekalinin/nodeenv) prompt for displaying node version and environment name.
    * `nvm` - Show the version of Node that is currently active, if it differs from the version used by NVM
* **PHP Segments:**
    * `php_version` - Show the current PHP version.
    * `laravel_version` - Show the current Laravel version.
    * [`symfony2_tests`](#symfony2_tests) - Show a ratio of test classes vs code classes for Symfony2.
    * `symfony2_version` - Show the current Symfony2 version, if you are in a Symfony2-Project dir.
* **Python Segments:**
    * `virtualenv` - Your Python [VirtualEnv](https://virtualenv.pypa.io/en/latest/).
    * [`anaconda`](segments/anaconda/README.md) - Your active [Anaconda](https://www.continuum.io/why-anaconda) environment.
    * `pyenv` - Your active python version as reported by the first word of [`pyenv version`](https://github.com/yyuu/pyenv). Note that the segment is not displayed if that word is _system_ i.e. the segment is inactive if you are using system python.
* **Ruby Segments:**
    * [`chruby`](#chruby) - Ruby environment information using `chruby` (if one is active).
    * [`rbenv`](#rbenv) - Ruby environment information using `rbenv` (if one is active).
    * [`rspec_stats`](#rspec_stats) - Show a ratio of test classes vs code classes for RSpec.
    * `rvm` - Ruby environment information using `$GEM_HOME` and `$MY_RUBY_HOME` (if one is active).
* **Rust Segments:**
    * `rust_version` - Display the current rust version and [logo](https://www.rust-lang.org/logos/rust-logo-blk.svg).
* **Swift Segments:**
    * `swift_version` - Show the version number of the installed Swift.
* **Java Segments:**
    * `java_version` - Show the current Java version.
* **Haskell Segments:**
    * `stack_project` - Show if you are in a Haskell Stack project directory.

**Cloud Segments:**
* **AWS Segments:**
    * [`aws`](segments/aws/README.md) - The current AWS profile, if active.
    * [`aws_eb_env`](segments/aws_eb_env/README.md) - The current Elastic Beanstalk Environment.
* `docker_machine` - The current Docker Machine.
* `kubecontext` - The current context of your `kubectl` configuration.
* `dropbox` - Indicates Dropbox directory and syncing status using `dropbox-cli`

**Other:**
* [`custom_command`](#custom_command) - Create a custom segment to display the
  output of an arbitrary command.
* [`command_execution_time`](#command_execution_time) - Display the time the current command took to execute.
* [`todo`](http://todotxt.com/) - Shows the number of tasks in your todo.txt tasks file.
* `detect_virt` - Virtualization detection with systemd
* `newline` - Continues the prompt on a new line.
* `openfoam` - Shows the currently sourced [OpenFOAM](https://openfoam.org/) environment.
* [`vagrant`](#vagrant) - Detects if you are in a folder with a running VM.

--------------------------------------------------------------------------------

##### chruby

This segment shows the version of Ruby being used when using `chruby` to change your current Ruby stack.

It uses `$RUBY_ENGINE` and `$RUBY_VERSION` as set by `chruby`.

| Variable | Default Value | Description |
|----------|---------------|-------------|
|`P9K_CHRUBY_SHOW_ENGINE`|true|Show the currently selected Ruby engine (e.g. `ruby`, `jruby`, `rbx`, etc)
|`P9K_CHRUBY_SHOW_VERSION`|true|Shows the currently selected engine's version (e.g. `2.5.1`)

##### command_execution_time

Display the time the previous command took to execute if the time is above
`P9K_COMMAND_EXECUTION_TIME_THRESHOLD`. The time is formatted to be
"human readable", and so scales the units based on the length of execution time.
If you want more precision, just set the
`P9K_COMMAND_EXECUTION_TIME_PRECISION` field.

| Variable | Default Value | Description |
|----------|---------------|-------------|
|`P9K_COMMAND_EXECUTION_TIME_THRESHOLD`|3|Threshold above which to print this segment. Can be set to `0` to always print.|
|`P9K_COMMAND_EXECUTION_TIME_PRECISION`|2|Number of digits to use in the fractional part of the time value.|

##### custom_command

The `custom_...` segment allows you to turn the output of a custom command into
a prompt segment. As an example, if you wanted to create a custom segment to
display your WiFi signal strength, you might define a custom segment called
`custom_wifi_signal` like this:
```zsh
P9K_LEFT_PROMPT_ELEMENTS=(context time battery dir vcs virtualenv custom_wifi_signal)
P9K_CUSTOM_WIFI_SIGNAL="echo signal: \$(nmcli device wifi | grep yes | awk '{print \$8}')"
P9K_CUSTOM_WIFI_SIGNAL_BACKGROUND="blue"
P9K_CUSTOM_WIFI_SIGNAL_FOREGROUND="yellow"
```
If you prefer, you can also define the function in your `.zshrc` rather than
putting it in-line with the variable export, as shown above. Just don't forget
to invoke your function from your segment! Example code that achieves the same
result as the above:
```zsh
zsh_wifi_signal(){
    local signal=$(nmcli device wifi | grep yes | awk '{print $8}')
    local color='%F{yellow}'
    [[ $signal -gt 75 ]] && color='%F{green}'
    [[ $signal -lt 50 ]] && color='%F{red}'
    echo -n "%{$color%}\uf230  $signal%{%f%}" # \uf230 is 
}

P9K_CUSTOM_WIFI_SIGNAL="zsh_wifi_signal"
P9K_LEFT_PROMPT_ELEMENTS=(context time battery dir vcs virtualenv custom_wifi_signal)
```
The command, above, gives you the wireless signal segment shown below:

![signal](http://i.imgur.com/hviMATC.png)

You can define as many custom segments as you wish. If you think you have
a segment that others would find useful, please consider upstreaming it to the
main theme distribution so that everyone can use it!

##### date

The `date` segment shows the current system date.

| Variable | Default Value | Description |
|----------|---------------|-------------|
|`P9K_DATE_FORMAT`|`%D{%d.%m.%y}`|[ZSH time format](http://zsh.sourceforge.net/Doc/Release/Prompt-Expansion.html#Date-and-time) to use in this segment.|

##### dir

The `dir` segment shows the current working directory. When using the "Awesome
Powerline" fonts, there are additional glyphs, as well:

| `Compatible` | `Powerline` | `Awesome Powerline` | Situation
|------------|-----------|-------------------|----------------------------
| None       | None      | ![](https://cloud.githubusercontent.com/assets/1544760/12183451/40ec4016-b58f-11e5-9b9e-74e2b2f0b8b3.png) | At the root of your home folder |
| None       | None      | ![](https://cloud.githubusercontent.com/assets/1544760/12369315/8a5d762c-bbf5-11e5-8a20-ca1179f48d6c.png) | Within a subfolder of your home directory |
| None       | None      | ![](https://cloud.githubusercontent.com/assets/1544760/12183452/40f79286-b58f-11e5-9b8c-ed1343a07b08.png) | Outside of your home folder |
| None       | None      | ⚙ | Within the `/etc` directory |

To turn off these icons you could set these variables to an empty string.
```zsh
P9K_DIR_HOME_ICON=''
P9K_DIR_HOME_SUBFOLDER_ICON=''
P9K_FOLDER_ICON=''
P9K_DIR_ETC_ICON=''
```
You can limit the output to a certain length by truncating long paths.
Customizations available are:

| Variable | Default Value | Description |
|----------|---------------|-------------|
|`P9K_DIR_PATH_ABSOLUTE`|None|If set to `true`, will use absolute paths instead of home folder abbreviation `~`|
|`P9K_DIR_SHORTEN_LENGTH`|`2`|If your shorten strategy, below, is entire directories, this field determines how many directories to leave at the end. If your shorten strategy is by character count, this field determines how many characters to allow per directory string.|
|`P9K_DIR_SHORTEN_STRATEGY`|None|How the directory strings should be truncated. See the table below for more informations.|
|`P9K_DIR_SHORTEN_DELIMITER`|`..`|Delimiter to use in truncated strings. This can be any string you choose, including an empty string if you wish to have no delimiter.|

| Strategy Name | Description |
|---------------|-------------|
|Default|Truncate whole directories from left. How many is defined by `P9K_DIR_SHORTEN_LENGTH`|
|`truncate_absolute_chars`|Truncates an absolute number of characters from the left such that the number of characters that your path displays (with or without `P9K_DIR_SHORTEN_DELIMITER`) is no more than `P9K_DIR_SHORTEN_LENGTH` + the length of `P9K_DIR_SHORTEN_DELIMITER` |
|`truncate_middle`|Truncates the middle part of a folder. E.g. you are in a folder named `~/MySuperProjects/AwesomeFiles/BoringOffice`, then it will truncated to `~/MyS..cts/Awe..les/BoringOffice`, if `P9K_DIR_SHORTEN_LENGTH=3` is also set (controls the amount of characters to be left).|
|`truncate_from_right`|Just leaves the beginning of a folder name untouched. E.g. your folders will be truncated like so: "/ro../Pr../office". How many characters will be untouched is controlled by `P9K_DIR_SHORTEN_LENGTH`.|
|`truncate_absolute`|Truncates everything exept the last few characters in the path. E.g. if you are in a folder named "~/Projects/powerlevel9k" and you have set `P9K_DIR_SHORTEN_LENGTH=3`, you will get "..l9k".|
|`truncate_to_last`|Truncates everything before the last folder in the path.|
|`truncate_to_first_and_last`|Truncate middle directories from the path. How many directories will be untouched is controlled by `P9K_DIR_SHORTEN_LENGTH`. E.g. if you are in a folder named `~/Projects/powerlevel9k` and you have set `P9K_DIR_SHORTEN_LENGTH=1`, you will get `~/../powerlevel9k`.||
|`truncate_to_unique`|Parse all parent path components and truncate them to the shortest unique length. If you copy & paste the result to a shell, after hitting `TAB` it should expand to the original path unambiguously.|
|`truncate_with_package_name`|Search for a `package.json` or `composer.json` and prints the `name` field to abbreviate the directory path. The precedence and/or files could be set by `P9K_DIR_PACKAGE_FILES=(package.json composer.json)`. If you have [jq](https://stedolan.github.io/jq/) installed, it will dramatically improve the speed of this strategy.|
|`truncate_with_folder_marker`|Search for a file that is specified by `P9K_DIR_SHORTEN_FOLDER_MARKER` and truncate everything before that (if found, otherwise stop on $HOME and ROOT).|

For example, if you wanted the truncation behavior of the `fish` shell, which
truncates `/usr/share/plasma` to `/u/s/plasma`, you would use the following:
```zsh
P9K_DIR_SHORTEN_LENGTH=1
P9K_DIR_SHORTEN_DELIMITER=""
P9K_DIR_SHORTEN_STRATEGY="truncate_from_right"
```
In each case you have to specify the length you want to shorten the directory
to. So in some cases `P9K_DIR_SHORTEN_LENGTH` means characters, in
others whole directories.

The `truncate_with_package_name` strategy gives your directory path relative to the root of your project.  For example, if you have a project inside `$HOME/projects/my-project` with a `package.json` that looks like:

```json
{
  "name": "my-cool-project"
}
```

The path shown would be `my-cool-project`.  If you navigate to `$HOME/projects/my-project/src`, then the path shown would be `my-cool-project/src`.  Please note that this currently looks for `.git` directory to determine the root of the project.

If you want to customize the directory separator, you could set:
```zsh
# Double quotes are important here!
P9K_DIR_PATH_SEPARATOR="%F{red} $(print_icon 'LEFT_SUBSEGMENT_SEPARATOR') %F{black}"
```
To omit the first character (usually a slash that gets replaced if you set `P9K_DIR_PATH_SEPARATOR`),
you could set `P9K_DIR_OMIT_FIRST_CHARACTER=true`.

You can also customize the leading tilde character when you are in `$HOME` using:
```zsh
# Double quotes are important here!
P9K_DIR_HOME_FOLDER_ABBREVIATION="%F{red} $(print_icon 'DIR_HOME_ICON') %F{black}"
```
You can also configure the `dir` segment to show when you are in a directory without write permissions, using the variable below.

| Variable | Default Value | Description |
|----------|---------------|-------------|
|`P9K_DIR_SHOW_WRITABLE`|`false`|If set to `true` and you are in a directory that you do not have write permissions for, this segment will display a lock icon and enter the `NOT_WRITABLE` state (which can be customized per [our usual process](https://github.com/bhilburn/powerlevel9k/wiki/Stylizing-Your-Prompt#segment-color-customization)). Note that this functionality is also available in a separate segment, `dir_writable`.|

If you want to customize the last directory of the path, you can now set `P9K_DIR_PATH_HIGHLIGHT_FOREGROUND` to a custom color and/or `P9K_DIR_PATH_HIGHLIGHT_BOLD=true` to display that part in bold.

You can also color the separator separately by setting the color using `P9K_DIR_PATH_SEPARATOR_FOREGROUND`.

##### disk_usage

The `disk_usage` segment will show the usage level of the partition that your current working directory (or a directory of your choice) resides in. It can be configured with the following variables.

| Variable | Default Value | Description |
|----------|---------------|-------------|
|P9K_DISK_USAGE_ONLY_WARNING|false|Hide the segment except when usage levels have hit warning or critical levels.|
|P9K_DISK_USAGE_WARNING_LEVEL|90|The usage level that triggers a warning state.|
|P9K_DISK_USAGE_CRITICAL_LEVEL|95|The usage level that triggers a critical state.|
|P9K_DISK_USAGE_PATH|`.` (working directory)|Set a path to use a fixed directory instead of the working 

##### newline

Puts a newline in your prompt so you can continue using segments on the next
line. This allows you to use segments on both lines, unlike
`P9K_PROMPT_ON_NEWLINE`, which simply separates segments from the
prompt itself.

This only works on the left side.  On the right side it does nothing.

##### rbenv

This segment shows the version of Ruby being used when using `rbenv` to change your current Ruby stack.

It figures out the version being used by taking the output of the `rbenv version-name` command.

* If `rbenv` is not in $PATH, nothing will be shown.
* By default, if the current local Ruby version is the same as the global Ruby version, nothing will be shown. See the configuration variable, below, to modify this behavior.

Variable | Default Value | Description |
|----------|---------------|-------------|
|`P9K_RBENV_ALWAYS`|'false'|Always show the `rbenv` segment, even if the local version matches the global.|

| Variable | Default Value | Description |
|----------|---------------|-------------|
|`P9K_RBENV_PROMPT_ALWAYS_SHOW`|`false`|Set to true if you wish to show the rbenv segment even if the current Ruby version is the same as the global Ruby version|

##### pyenv

This segment shows the version of Python being used when using `pyenv` to change your current Python stack.

The `PYENV_VERSION` environment variable will be used if specified. Otherwise it figures out the version being used by taking the output of the `pyenv version-name` command.

* If `pyenv` is not in $PATH, nothing will be shown.
* If the current Python version is the same as the global Python version, nothing will be shown.

| Variable | Default Value | Description |
|----------|---------------|-------------|
|`P9K_PYENV_PROMPT_ALWAYS_SHOW`|`false`|Set to true if you wish to show the pyenv segment even if the current Python version is the same as the global Python version|

##### rspec_stats

See [Unit Test Ratios](#unit-test-ratios), below.

##### ram

| Variable | Default Value | Description |
|----------|---------------|-------------|
|`P9K_RAM_ELEMENTS`|Both|Specify `ram_free` or `swap_used` to only show one or the other rather than both.|

##### symfony2_tests

See [Unit Test Ratios](#unit-test-ratios), below.

##### vagrant

This segment detects if you are in a folder with a running/stopped VM. If so,
it displays `UP`, when VM is running or `DOWN` when VM is stopped.

You can customize these strings with:

| Variable           | Default Value | Description   |
|--------------------|---------------|---------------|
| `P9K_VAGRANT_UP`   | `UP`          | VM is running |
| `P9K_VAGRANT_DOWN` | `DOWN`        | VM is stopped |

##### vcs

By default, the `vcs` segment will provide quite a bit of information. Further
customization is provided via:

| Variable | Default Value | Description |
|----------|---------------|-------------|
|`P9K_VCS_HIDE_BRANCH_ICON`|`false`|Set to `true` to hide the branch icon from the segment.|
|`P9K_VCS_SHOW_CHANGESET`|`false`|Set to `true` to display the hash / changeset in the segment.|
|`P9K_VCS_CHANGESET_HASH_LENGTH`|`12`|How many characters of the hash / changeset to display in the segment.|
|`P9K_VCS_SHOW_SUBMODULE_DIRTY`|`true`|Set to `false` to not reflect submodule status in the top-level repository prompt.|
|`P9K_VCS_HIDE_TAGS`|`false`|Set to `true` to stop tags being displayed in the segment.|
|`P9K_VCS_GIT_HOOKS`|`(vcs-detect-changes git-untracked git-aheadbehind git-stash git-remotebranch git-gitdir git-tagname)`|Layout of the segment for git repositories.|
|`P9K_VCS_HG_HOOKS`|`(vcs-detect-changes)`|Layout of the segment for Mercurial repositories.|
|`P9K_VCS_SVN_HOOKS`|`(vcs-detect-changes svn-detect-changes)`|Layout of the segment for SVN repositories.|
|`P9K_VCS_ACTIONFORMAT_FOREGROUND`|`red`|The color of the foreground font during actions (e.g., `REBASE`).|
|`P9K_VCS_GIT_ALWAYS_SHOW_REMOTE_BRANCH`|`false`|Set to true If you would to always see the remote branch.|


##### vcs symbols

The `vcs` segment uses various symbols to tell you the state of your repository.
These symbols depend on your installed font and selected `P9K_MODE`
from the [Installation](#Installation) section above.

| `Compatible` | `Powerline` | `Awesome Powerline` | Explanation
|--------------|---------------------|-------------------|--------------------------
| `↑4`         | `↑4`                | ![icon_outgoing](https://cloud.githubusercontent.com/assets/1544760/7976089/b5904d6e-0a76-11e5-8147-5e873ac52d79.gif)4  | Number of commits your repository is ahead of your remote branch
| `↓5`         | `↓5`                | ![icon_incoming](https://cloud.githubusercontent.com/assets/1544760/7976091/b5909c9c-0a76-11e5-9cad-9bf0a28a897c.gif)5  | Number of commits your repository is behind of your remote branch
| `⍟3`         | `⍟3`                | ![icon_stash](https://cloud.githubusercontent.com/assets/1544760/7976094/b5ae9346-0a76-11e5-8cc7-e98b81824118.gif)3 | Number of stashes, here 3.
| `●`          | `●`                 | ![icon_unstaged](https://cloud.githubusercontent.com/assets/1544760/7976096/b5aefa98-0a76-11e5-9408-985440471215.gif) | There are unstaged changes in your working copy
| `✚`          | `✚`                 | ![icon_staged](https://cloud.githubusercontent.com/assets/1544760/7976095/b5aecc8a-0a76-11e5-8988-221afc6e8982.gif) | There are staged changes in your working copy
| `?`          | `?`                 | ![icon_untracked](https://cloud.githubusercontent.com/assets/1544760/7976098/b5c7a2e6-0a76-11e5-8c5b-315b595b2bc4.gif)  | There are files in your working copy, that are unknown to your repository
| `→`          | `→`                 | ![icon_remote_tracking_branch](https://cloud.githubusercontent.com/assets/1544760/7976093/b5ad2c0e-0a76-11e5-9cd3-62a077b1b0c7.gif) | The name of your branch differs from its tracking branch.
| `☿`          | `☿`                 | ![icon_bookmark](https://cloud.githubusercontent.com/assets/1544760/7976197/546cfac6-0a78-11e5-88a6-ce3a1e0a174e.gif) | A mercurial bookmark is active.
| `@`         | ![icon_branch_powerline](https://cloud.githubusercontent.com/assets/1544760/8000852/e7e8d8a0-0b5f-11e5-9834-de9b25c92284.gif) | ![](https://cloud.githubusercontent.com/assets/1544760/7976087/b58bbe3e-0a76-11e5-8d0d-7a5c1bc7f730.gif) | Branch Icon
| None         |  None               | ![icon_commit](https://cloud.githubusercontent.com/assets/1544760/7976088/b58f4e50-0a76-11e5-9e70-86450d937030.gif)2c3705 | The current commit hash. Here "2c3705"
| None         |  None               | ![icon_git](https://cloud.githubusercontent.com/assets/1544760/7976092/b5909f80-0a76-11e5-9950-1438b9d72465.gif) | Repository is a git repository
| None         |  None               | ![icon_mercurial](https://cloud.githubusercontent.com/assets/1544760/7976090/b5908da6-0a76-11e5-8c91-452b6e73f631.gif) | Repository is a Mercurial repository

##### vcs truncation

You can limit the branch name to a certain length by truncating long names.
Customizations available are:

| Variable | Default Value | Description |
|----------|---------------|-------------|
|`P9K_VCS_SHORTEN_LENGTH`|None|This field determines how many characters to show.|
|`P9K_VCS_SHORTEN_MIN_LENGTH`|None|This field determines minimum branch length. Branch name will be truncated if its length greater than this field.|
|`P9K_VCS_DIR_SHORTEN_STRATEGY`|None|This field determines how branch name should be truncated. See the table below for more information.|
|`P9K_DIR_SHORTEN_DELIMITER`|`...`|Delimiter to use in truncated strings. This can be any string you choose, including an empty string if you wish to have no delimiter.|

| Strategy Name | Description |
|---------------|-------------|
|`truncate_middle`|Truncates the middle part of a branch. E.g. branch name is `1234-super_super_long_branch_name`, then it will truncated to `1234-..._name`, if `P9K_VCS_SHORTEN_LENGTH=5` is also set (controls the amount of characters to be left).|
|`truncate_from_right`|Just leaves the beginning of a branch name untouched. E.g. branch name will be truncated like so: `1234-...`. How many characters will be untouched is controlled by `P9K_VCS_SHORTEN_LENGTH`.|

For example, if you want to truncate `1234-super_super_long_branch_name` to `1234-..` and don't do it with `development`:
```zsh
P9K_VCS_SHORTEN_LENGTH=4
P9K_VCS_SHORTEN_MIN_LENGTH=11
P9K_VCS_DIR_SHORTEN_STRATEGY="truncate_from_right"
P9K_VCS_DIR_SHORTEN_DELIMITER=".."
```

#### Unit Test Ratios

The `symfony2_tests` and `rspec_stats` segments both show a ratio of "real"
classes vs test classes in your source code. This is just a very simple ratio,
and does not show your code coverage or any sophisticated stats. All this does
is count your source files and test files, and calculate the ratio between them.
Just enough to give you a quick overview about the test situation of the project
you are dealing with.

### Disabling / Enabling Powerlevel9k

You can disable P9k and return to a very basic prompt at any time simply by
calling:

```zsh
$ prompt_powerlevel9k_teardown
```

You can then re-enable it by calling:

```zsh
$ prompt_powerlevel9k_setup
```

### tl; dr

Want to just get a quick start? Check out the [Show Off Your
Config](https://github.com/bhilburn/powerlevel9k/wiki/Show-Off-Your-Config)
portion of the wiki to get going.

[The Wiki also has a ton of other useful
information!](https://github.com/bhilburn/powerlevel9k/wiki)

### License

Project: MIT

Logo: CC-BY-SA. Source repository: https://github.com/bhilburn/powerlevel9k-logo
