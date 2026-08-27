# Git-commando's

> ⚠️ **Belangrijk — het bestand `CNAME` nooit verwijderen.**
> Daarin staat `www.ranstverdientschool.be`. Zonder dat bestand valt de site terug
> op `ranstverdientschool.github.io` en is het eigen domein weg.
> Neem `CNAME` daarom mee in elke commit-reeks en doe **altijd eerst `git pull`**
> vóór een `git push --force` (force overschrijft wat er online staat).

```bash
cd "/Users/dagmar/Library/Mobile Documents/com~apple~CloudDocs/MijnBestanden/Data/Valentin en Jozefien/Lab School Ranst" && git pull --rebase && git add index.html CNAME && git commit -m "Beschrijving" && git push 'https://ranstverdientschool:<token>@github.com/ranstverdientschool/ranstverdientschool.github.io.git' main
```

Controleren:

```bash
git diff index.html
git --no-pager log --oneline -5
git ls-remote https://github.com/ranstverdientschool/ranstverdientschool.github.io.git
```

Domein controleren:

```bash
dig +short www.ranstverdientschool.be          # moet ranstverdientschool.github.io + GitHub-IP's geven
dig +short ranstverdientschool.be A            # moet 185.199.108-111.153 geven
curl -sI https://www.ranstverdientschool.be/ | head -1
```

Ongedaan maken:

```bash
git restore index.html        # wijziging weg (nog niet gecommit)
git reset --soft HEAD~1       # laatste commit terug, wijziging behouden
```

```bash
git restore index.html        # wijziging weg (nog niet gecommit)
git reset --soft HEAD~1       # laatste commit terug, wijziging behouden
```
