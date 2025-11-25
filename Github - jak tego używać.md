
# 1. Instalacja Git i konfiguracja

## Windows
- Pobierz: [Git for Windows](https://git-scm.com/download/win)
- Instalacja: wszystkie domyślne opcje OK
- Uruchom **Git Bash** (terminal podobny do Linuxa)

## Linux
- wykonaj w terminalu: ```sudo apt install git```

---

## Konfiguracja

W zależności od systemu w **terminalu** lub w programie **Git Bash** wykonaj:
	1. `git config --global user.name "NAME" ` w miejscu NAME wpisz nazwę, która będzie się wyświetlała przy commitach
	2. `git config --global user.email "EMAIL"` w miejscu EMAIL wpisz adres email, powiązany z twoim kontem GitHub
	3. `git config --list` (opcjonalnie) sprawdź czy podane wcześnij dane są prawidłowe

---
---
# 2. Klonowanie repozytorium

Wykonaj polecenie `git clone URL_REPO`

---
---
# 3. Podstawowe polecenia

|Polecenie|Opis|
|---|---|
|`git status`|Pokazuje zmienione pliki|
|`git add .` lub `git add <plik>`|Dodaje pliki do commita|
|`git commit -m "Opis zmian"`|Tworzy commit z opisem|
|`git pull`|Pobiera zmiany z GitHub do lokalnego repo|
|`git push`|Wysyła lokalne commity na GitHub|
|`git log --oneline`|Historia commitów (do sprawdzenia wersji przed push)|

---
---

# 4. Przykładowa procedura

1. Wejdź do folderu repo - `cd ~/GitHub/for-tutorial`

2. Sprawdź zmiany - `git status`

3. Edytuj plik lokalnie (np. README.md)

4. Dodaj zmiany do commita - `git add README.md`

5. Zatwierdź zmiany - `git commit -m "Edytowałem README"`

6. Pobierz ewentualne zmiany z GitHub - `git pull`

7. Wyślij zmiany na GitHub - `git push`
