## Cheatsheets for [navi](https://github.com/denisidoro/navi)
### Usage
To copy the cheatsheets using navi into the default navi directory, run the following command:

```bash
navi repo add Twilight4/cheats
```

To add your own repository as a featured cheatsheet repo, please edit the [featured_repos](https://github.com/denisidoro/cheats/edit/master/featured_repos.txt) file. The contents of this list will be displayed when running `navi repo browse`.

### Auto-updating repositories
To set up an auto-updating repository using `git` and `crontab`, follow these steps:

1. Clone your repo using `git` to the desired folder. If you prefer a custom path instead of the default navi directory, make sure to define it in the navi configuration.
```bash
user="Twilight4"
repo="cheats"
git clone "git@github.com:${user}/${repo}" ~/workspace/Twilight4__cheats
```

2. Add a cron job using `crontab`.
```bash
crontab -e
*/0 11 * * * bash -c 'cd ~/workspace/cheats/Twilight4__cheats && /usr/local/bin/git pull -q origin master'
```

Note: The example cron job above triggers the update every day at 11 am. If you want to modify the schedule, you can refer to [crontab guru](https://crontab.guru/). Additionally, ensure that the full paths to `navi` and `git` match your setup. You can verify their paths by using the `which navi` and `which git` commands.

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
