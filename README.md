# git-json-merge
A git merge driver for json files inspired by [git-po-merge](https://github.com/beck/git-po-merge).

## Install

This can be done one of two ways, globally or per-project/directory:

### Globally

Install:
```sh
npm install --global git-json-merge
```

Add to `~/.gitconfig`:
```ini
[core]
    attributesfile = ~/.gitattributes
[merge "json"]
    name = custom merge driver for json files
    driver = git-json-merge %A %O %B
```

Create `~/.gitattributes`:
```ini
*.json merge=json
```

### Single project / directory

Install:
```sh
npm install git-json-merge --save-dev
```

Update git config:
```sh
git config merge.json.driver "$(npm bin)/git-json-merge %A %O %B"
git config merge.json.name "custom merge driver for json files"
```

Add the same `.gitattributes` where desired and commit.  
Note `.gitattributes` is only used after committed.


Helpful docs:
* http://git-scm.com/docs/gitattributes#_defining_a_custom_merge_driver
* http://stackoverflow.com/questions/28026767/where-should-i-place-my-global-gitattributes-file

Thanks:
* https://gist.github.com/mezis/1605647
* http://stackoverflow.com/questions/16214067/wheres-the-3-way-git-merge-driver-for-po-gettext-files
