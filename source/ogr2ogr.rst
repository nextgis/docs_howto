.. sectionauthor:: Артём Светлов <@nextgis.ru>

.. ogr2ogr:

ogr2ogr
====================================================================

Компанией NextGIS был создал драйвер nextgisweb для GDAL. Теперь используя ogr2ogr можно создавать слои в NextGIS Web.



ogr2ogr geojson to ngw
----------------------

```
ogr2ogr -nlt POINT -skipfailures  -dsco "USERPWD=administrator:demodemo" -t_srs EPSG:4326 -f NGW "NGW:https://sandbox.nextgis.com/resource/0/Название на русском языке" post_office.geojson 
```


