# Confgit

[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)
[![PR info](https://img.shields.io/github/issues-pr/yagarea/confgit)](https://github.com/yagarea/confgit/pulls)
[![CodeFactor](https://www.codefactor.io/repository/github/yagarea/confgit/badge/master)](https://www.codefactor.io/repository/github/yagarea/confgit/overview/master)
[![Python 3.x](https://img.shields.io/badge/python-3.x-green.svg)](https://www.python.org/)
[![Closed issues](https://img.shields.io/github/issues-closed/yagarea/confgit)](https://github.com/yagarea/confgit/issues)
[![Repo starts](https://img.shields.io/github/stars/yagarea/confgit?style=social)](https://github.com/yagarea/confgit/stargazers)

Confgit is a Git overhead for version control of your config files. The main difference 
between confgit and any other config file version system is it's simplicity. It makes 
version control and migration of config files safe and easy.

## Usage

#### init
Initialize git repository for your config files in current directoty and generates 
config file in "~/.config/confgit.yml" if you do not specify other location using 
`--config` argument.

Examples:
```
confgit init
```

```
confgit init --config /alternative/location/of/config/file/confgit.yml
```

#### sync
Writes content of complementary files of registered files to their origins.

Example:
```
confgit sync
```

#### update
Writes content of origins of registered files to their's complementary files.

Example:
```
confgit update
```

#### backup
Creates a zip file with backup of all files in confgit repository. You can specify name
of the backup file.

Example:
```
confgit backup
```

```
confgit backup my_backup_monday.zip
```
(If name of backup does not end with `.zip` it will be automatically added)


#### include _file to include_
Registers a file or a directory into a confgit watch list.

Example:
```
confgit include nvim.init
```

```
confgit include ~/.config/
```
(If you give directory as parameter it will register all its files recursively)


#### exclude _file to exclude_
Excludes a file or directory from the registered files.

Example:
```
confgit exclude zoom.conf
```

```
confgit exclude .config/rofi/
```
(If you give directory as parameter it will exclude all its files recursively)


#### optional arguments:
- **-h**, **--help**                                - show this help message and exit 
- **-c** _CONFIG_PATH_, **--config** _CONFIG_PATH_  - load alternative config
- **--debug**                                       - show additional information for debugging


#### Git original commands supported by confgit
clone, add, mv, restore, rm, sparse-checkout, bisect, diff, grep, log, show, status, branch, commit, merge, rebase, reset, switch, tag, fetch, pull, push

---
**Disclaimer:** Author does not have any responsibility for any damage or data loss caused by the usage of this software.
