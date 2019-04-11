# Dotfiles

Dotfile management using git.

</br>

Clone dotfiles repo to new machine:

```bash
git clone --separate-git-dir=.dotfiles.git git@github.com:jhughes01/dotfiles.git && rm -rf dotfiles
```

Within my aliases, I have the alias `dotfiles`, which wraps the git command for this dir. 

Add file:
```bash
dotfiles add -f dotfile.txt
```

Update docfiles:
```bash
dotfiles pull
```
