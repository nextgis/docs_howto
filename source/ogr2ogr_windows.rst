.. sectionauthor:: Артём Светлов <@nextgis.ru>

.. ogr2ogr_windows:

Запуск утилит командной строки ogr2ogr на Windows
=====================================================

Введение
----------------------------

Вместе с NextGIS QGIS устанавливается интепритатор языка Python и утилиты командной строки ogr: ogr2ogr, gdalinfo, ogrlineref и другие. 
Они запускаются самим NextGIS QGIS, но так же вы можете запустить их из консоли.
На Ubuntu утилиты gdal/ogr и Python ставятся по зависимостям при установке NextGIS QGIS, и их можно запускать из системной консоли. 
На Windows они не прописываются в path, и из системной консоли они не видны. Это сделано так что бы при совместной установке NextGIS QGIS и обычного QGIS они не ломали друг друга.

Что бы запустить утилиту ogr2ogr на Windows необходимо:

1. Инсталировать NextGIS QGIS 
2. Запустить поиск Windows (Win+S) 
3. По строке "NextGIS" найти и запустить NextGIS Command Promt
4. Откроется окно с коммандной строкой. В нём можно запускать ogr2ogr и другие утилиты GDAL.

Так же в этом окне запускается python.
Вы можете создать скрипт на python, который будет вызывать ogr2ogr вот так: 

.. code-block:: python

import os
os.system('ogr2ogr output.shp test.vrt')
os.system('ogr2ogr output.geojson sample.shp')

И вызвать его из NextGIS Command Promt


.. code-block:: batch

python c:/folder/main.py
