# SSH kapcsolat létesítése
##  SSH kulcsok generálása
Futtasd az alábbi parancsot az SSH kulcsok generálásához::
`ssh-keygen -t ed25519 -C "smitpeter777@gmail.com"
   `bash

## Publikus kulcs másolása

``cat ~/.ssh/id_ed25519.pub
``

## 3. Publikus kulcs hozzáadása a GitHub-hoz
Menj a GitHub-on a Settings -> SSH and GPG keys menüponthoz.

Kattints a New SSH key gombra.

Add meg a kulcs nevét (pl. "My Laptop SSH Key"), majd illeszd be a másolt publikus kulcsot és kattints az Add SSH key gombra.

## 4. Győződj meg arról, hogy az SSH agent fut és a kulcs hozzá van adva
``eval "$(ssh-agent -s)"``

Add hozzá a privát kulcsot az SSH agenthez:


``ssh-add ~/.ssh/id_ed25519
``

## 5. Teszteld az SSH kapcsolatot
``ssh -T git@github.com
``
Ha a kapcsolat sikeres, a következő üzenetet kell látnod:
``Hi username! You've successfully authenticated, but GitHub does not provide shell access.``

Használd a git restore --staged parancsot, hogy eltávolítsd a fájlt a staging area-ból:


``git restore --staged blue.txt``

``git restore blue.txt``

git status
git diff blue.txt


## Barnc kezelés

`git branch [branch_name]` - létrehoz egy új branch-et

`git branch` - listázza a branch-eket

`git checkout [branch_name]` - átváltás a megadott branch-re

`git checkout -b [branch_name]` - létrehoz egy új branch-et és átvált rá

`git merge [branch_name]` - összefűzi a megadott branch-et a jelenlegivel

`git branch -d [branch_name]` - törli a megadott branch-et

`git branch -D [branch_name]` - erőltetett törlés a megadott branch-ről

`git branch -m [new_branch_name]` - átnevezi a jelenlegi branch-et

`git branch -a` - listázza az összes branch-et

`git branch -r` - listázza a távoli branch-eket