# Installazione

Scaricare prima di tutto l'ultima versione stabile di Arches (6.1.0):

    https://github.com/archesproject/arches/archive/refs/tags/6.1.0.zip

quindi estrarre il contenuto dell'archivio in una cartella (di default, l'archivio verrà estratto in `./arches-6.1.0`).

Per le attività di sviluppo in locale, si consiglia di seguire la procedura descritta sotto.

## Sviluppo in locale

Creare dapprima un fork del progetto [CNR-DHILab/dataspace](https://github.com/CNR-DHILab/dataspace) dal proprio account GitHub, quindi clonare il fork all'interno della cartella principale di Arches:

    cd ./arches-6.1.0
    git clone https://github.com/<user_github>/dataspace.git

sostituendo `<user_github>` con il proprio nome utente.

Il progetto `dataspace` sarà quindi tracciato da Git e il fork su GitHub sarà associato al repository locale come origine remota di default verso le quale fare i `push`.

Si può scegliere di lavorare sulla branch principale - `main` - oppure creare una branch di sviluppo; in entrambi i casi, per far sì che le modifiche siano integrate con il repository originario (`CNR-DHILab/dataspace`), sarà necessario fare il `push` verso il proprio fork e aprire una `pull request`.

## Virtual Env

Una volta impostato l'ambiente di sviluppo, creare un ambiente virtuale con `python` nella root di Arches (`arches-6.1.0`):

    python -m venv ENV

e attivarlo con il comando (Windows):

    ENV\Scripts\activate.bat

In ambiente Unix/Linux, usare il comando `source ENV/bin/activate`.

Procedere quindi all'installazione di Arches con `pip`:

    pip install arches

Avviare quindi Elasticsearch (Windows):

    path/to/elasticsearch.bat

In ambiente Unix/Linux:

    /path/to/elasticsearch/bin/elasticsearch -d

L'opzione `-d` permette di avviare Elasticsearch come servizio (demone).

## Configurazione locale

Per configurare correttamente l'installazione locale, rinominare dapprima i file di configurazione come segue:

    dataspace/template_settings.py       -> dataspace/settings.py
    dataspace/template_settings_local.py -> dataspace/settings_local.py

Modificare quindi i file di configurazione inserendo le credenziali per accedere al database PostgreSQL e gli altri parametri necessari.

## Installazione DB e avvio server

Installare infine il database di Arches posizionandosi nella sottocartella `dataspace`:
    
    cd dataspace
    python manage.py setup_db

e avviare il server di sviluppo:

    python manage.py runserver

La piattaforma dovrebbe essere raggiungibile in `localhost` sulla porta 8000 di default:

    localhost:8000

## Dipendenze software (Windows)
- Python
- PostgreSQL e PostGIS
- Elasticsearch 7x
- GDAL (OSGeo)
  - Non hai bisogno di QGIS o GRASS
- Node.js

## Dipendenze Unix/Linux

In ambiente Linux, nello specifico Debian/Ubuntu, potrebbe essere necessario installare i seguenti pacchetti, prima di installare Arches, per garantire il corretto funzionamento del modulo Python `psycopg2`:

    sudo apt update && sudo apt install libpq-dev libssl-dev python3-dev build-essentials -y

## Link utili

1. https://www.enterprisedb.com/downloads/postgres-postgresql-downloads
2. https://postgresapp.com/downloads.html
3. https://nodejs.org/
4. https://www.elastic.co/downloads/past-releases/elasticsearch-7-17-3
5. https://trac.osgeo.org/osgeo4w/
6. https://gdal.org/download.html#current-release
