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
