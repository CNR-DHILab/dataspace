**Installazione**

Scarica l'ultima versione stabile di arches

https://github.com/archesproject/arches/archive/refs/tags/6.1.0.zip

dezippa in una cartella

forkate il progetto dataspace

https://github.com/CNR-DHILab/dataspace

posizionatevi nella root principale di arches e fate un clone

  - git clone https://github.com/CNR-DHILab/dataspace.git

create un ambiente virtuale con python nella root principale

  - python -m venv ENV

attivare l'ambiente virtuale

  -  source ENV/Scripts/activate

Installate arches con pip

 - pip install arches

Avviate elasticsearch

 - path/to/elastichsearc.bat



### DIPENDENZE software (Windows)
- Python
- PostgreSQL e PostGIS
- Elasticsearch 7x
- GDAL (OSGeo)
  - Non hai bisogno di QGIS o GRASS
- Node.js



[1]: https://www.enterprisedb.com/downloads/postgres-postgresql-downloads
[2]: https://postgresapp.com/downloads.html
[3]: https://nodejs.org/
[4]: https://www.elastic.co/downloads/past-releases/elasticsearch-7-17-3
[5]: https://trac.osgeo.org/osgeo4w/
[6]: https://gdal.org/download.html#current-release
