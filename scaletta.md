# Scaletta per Git Best Practice

## Clonazione repo e installazioni

1. Clonare la repo 

```bash
git clone link-repo nome_cartella o . per cartella corrente
```

1. In caso di progetto Vue o Laravel installare le dipendenze

```bash
npm i
composer install
```

1. In caso di progetto Laravel copiare il file .ENV.EXAMPLE e rinominarlo in .ENV aggiungendo i dati del database e modificando la voce filesystem in Public.

```ENV
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE='nome database'
DB_USERNAME=root
DB_PASSWORD=root

FILESYSTEM_DISK=public
```
1. Genero la chiave

```bash
php artisan key:generate
```

1. Avvio il server

```bash
php artisan serve e npm run dev
```

## Creare una branch

1. lanciare il comando pwd per verificare la attuale Branch

```bash
pwd
```

1. Creare una nuova branch 

- Il nome della Branch deve essere chiaro riguardante il lavoro svolto all'interno di essa

```bash
git checkout -b Nome_Branch
```

1. Ora potete tranquillamente lavorare sulla branch senza apportare modifiche dirette al main

- Dopo aver effettuato le modifiche ritorniamo nel main

```bash
git checkout main
```

- effettuare un pull sulla main Branch con il comando

```bash
git pull
```

- o da interfaccia grafica. In questo modo sarete sincronizzati con le modifiche al main.

### Potrebbero verificarsi conflitti. Contattare il team per coordinarsi sulle modifiche!

1. Ritornare sulla branch creata precedentemente 

```bash
git checkout Nome_Branch
```

1. Effettuare un commit e Pushare le modifiche

- vi appararirà un messaggio di errore in console (non sempre! Contattare il team) con un comando alternativo da lanciare.

- Lanciare il comando nel messaggio di errore

### AVVISARE IL TEAM, I PUSH VANNO VERIFICATI SU GITHUB DA UN ALTRO MEMBRO

## Effettuare il Merge

- Prima di effettuare il push, committare la branch, pullare dal main e mergiare la main nel branch

### Dalla Branch

```bash

git add .

git commit -m"messaggio di commit" (commit della branch)

git checkout main (Torno nel main)

git pull (Mi sincronizzo con gli aggiornamenti del main)

git checkout nome_branch (Torno nella branch)

git merge main (Sincronizzo la mia Branch con il main)

git push (Pusho dalla branch il commit fatto prima)

```

## Se il lavoro sulla branch è completo procedo su github e chiudo la pull request e chiudo la branch

# DOPO LA CHIUSURA DEL LAVORO SU UNA BRANCH IMPORTANTE APRIRNE UN ALTRA E NON UTILIZZARE QUELLA USATA PRIMA O IL MAIN 


# ALLA FINE DEL PROGETTO

Oppure un altro metodo che potete utilizzare e aggiungere una repository upstream al vostro codice.
Cambia che in questo modo non eliminate la cartella .git e quindi non perdete i vostri commit e la connessione con la repository master (origin) e potete cosi continuare a fare pull in caso di necessita e push dei vostri branch anche al master.
1 - Per farlo aggiungiamo la repository creata previamente su Github

```bash

git remote add upstream http://mio_url_di_github.git

```

2 - Verifichiamo che si e' aggiunto correttamente

```bash

git remote -v

```

Vedremo ciò più o meno:

```bash

origin https://github.com/boolean-it/ex-laravel9-boolfolio-backend.git (fetch)
origin https://github.com/boolean-it/ex-laravel9-boolfolio-backend.git (push)
upstream https://github.com/arturmamedov/withFront (fetch)
upstream https://github.com/arturmamedov/withFront (push)

```

E quindi una di origin e una di upstream (la nostra personale)
3 -  Da interfaccia di VSCode Git push to ... oppure con il comando pushiamo i nostri commit e branch alla upstream:

```bash

git push upstream main

```

Attenzione main e' il nome del branch (noi ci aspettiamo che alla fine del lavoro tutti i vostri branch e quindi modifiche siano mergiati dentro il branch main o master e non nei vostri branch individuali, claro?)