## Cheatsheets for [navi](https://github.com/denisidoro/navi)
### Usage
If you want to copy the cheatsheets using navi into the default navi directory issue command:
```bash
navi repo add Twilight4/cheats
```
In order to add your own repository as a featured cheatsheet repo, please [edit this file](https://github.com/denisidoro/cheats/edit/master/featured_repos.txt). This list will be displayed when `navi repo browse` is run.

### Auto-updating repositories
To set up auto-updating repository using `git` and `crontab` clone your repo using `git` to the desired folder (if you don't want to use the default navi directory then you need to define the custom path in navi config):
```bash
user="Twilight4"
repo="cheats"
git clone "git@github.com:${user}/${repo}" ~/workspace/Twilight4__cheats
```
Then, add a cron job:
```bash
crontab -e
*/0 11 * * * bash -c 'cd ~/workspace/cheats/Twilight4__cheats && /usr/local/bin/git pull -q origin master'
```
Please note the cron job above is just an example and you should edit it accordingly:
- In this example, the cron job is triggered every day at 11am. [crontab guru](https://crontab.guru/) may come in handy if you want to change this value
- The full paths to `navi` and `git` may differ in your setup. Check their actual values using `which navi` and `which git`

### Translating original tldr files into [navi](https://github.com/denisidoro/navi) compatible format
If you want to add a cheatsheet for a new command, it's worth checking out [tldr](https://github.com/tldr-pages/tldr) pages. You can copy a cheatsheet from there, convert it to navi format and enhance it:
```bash
git clone https://github.com/tldr-pages/tldr.git ~/downloads/tldr && cd ~/downloads/tdlr
cp ~/workspace/Twilight4__cheats/translate.sh ./
./translate.sh
```
- then just copy the interesting cheatsheet to your repo
- you can check if your [tldr](https://github.com/tldr-pages/tldr) cheatsheet is in the repo running: `navi --tldr <query>`
- or use cheatsheets from [cheat.sh](https://github.com/chubin/cheat.sh) by running: `navi --cheatsh <query>`
