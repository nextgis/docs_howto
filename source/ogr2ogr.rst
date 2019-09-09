.. sectionauthor:: Артём Светлов <@nextgis.ru>

.. ogr2ogr:

этот текст наверно будет перенесён в папку с тренингами

ogr2ogr
====================================================================

NextGIS создал драйвер nextgisweb для gdal. Теперь используя ogr2ogr можно создавать слои в ngw.



ogr2ogr geojson to ngw
-------------------------------

```
ogr2ogr -nlt POINT -skipfailures  -dsco "USERPWD=administrator:demodemo" -t_srs EPSG:4326 -f NGW "NGW:https://sandbox.nextgis.com/resource/0/Название на русском языке" post_office.geojson 
```


