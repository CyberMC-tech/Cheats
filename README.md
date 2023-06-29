## Cheatsheets for [navi](https://github.com/denisidoro/navi).
### Usage
```
navi repo add Twilight4/cheats
```
In order to add your own repository as a featured cheatsheet repo, please [edit this file](https://github.com/denisidoro/cheats/edit/master/featured_repos.txt). This list will be displayed when `navi repo browse` is run.

### Translating original tldr files into [navi](https://github.com/denisidoro/navi) compatible format
If you want to add a cheatsheet for a new command, it's worth checking out [tldr](https://github.com/tldr-pages/tldr) pages. You can copy a cheatsheet from there, convert it to navi format and enhance it, then add it to your repo.
```
git clone https://github.com/tldr-pages/tldr.git ~/downloads tldr && cd tdlr
mv ~/.config/.local/share/navi/cheats/Twilight4__cheats/translate.sh ./
```
- then just copy the interesting cheatsheet to your repo
- you can check if your tldr cheatsheet is in the repo running: `navi --tldr <query>`
