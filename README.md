dothooks
========

Manage dotfiles in `~` with Git. Automatic updates. Multiple repositories. Won't overwrite your own files.

Bootstrap:

```
DOTFILES_REPOS='https://github.com/rimmington/dotfiles' source <(curl -s https://raw.githubusercontent.com/rimmington/dothooks/master/bootstrap)
```

Hook magic
----------

* All scripts are executed by Bash.
* Nothing in the user's home is touched until everything succeeds, so feel free to `errol` + `exit` whenever you want. `set -e` is nice too.
* `$HOME`/`~` is a staging directory where you should copy files to go in the user's home.
* `$HERE_LIB` is the future location of your hook repo.
* `pushd_` and `popd_` are silent versions of their well-known cousins.
* `info` and `errol` print happy and sad messages.
* `line_in_file FILE LINE` does what is says. It'll break if the file doesn't exist.
* `ensure_bash_sources` and `ensure_shell_sources` add to `.bashrc` or equivalent. You can do things like `ensure_bash_sources $HERE_LIB/my_bash_functions` or `ensure_bash_sources ~/.envvars`.
