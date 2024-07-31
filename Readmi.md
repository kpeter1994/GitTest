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