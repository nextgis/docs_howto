Выгрузки данных от NextGIS
====================================================

.. _ngdata_structure:

Файловая структура данных
------------------------------

Выгрузка, получаемая на `NextGIS Data <https://data.nextgis.com/ru/>`_, представляет собой ZIP-архив, который нужно распаковать перед использованием. Название архива содержит в себе информацию о дате выгрузки и формате, а также код региона, если он выбран из каталога, или обозначение custom, если область была выбрана вручную.

Распакованный архив представляет собой папку, содержащую следующие файлы и подпапки. 

Во всех выгрузках:

* Файл границы выбранной области ``order_boundary.geojson``.

* Папка со слоями данных ``data``. В ней лежат файлы данных и стилей, а также граница области заказа в выбранным формате.

* Текстовый файл, содержащий данные о лицензиях и копирайты ``readme.txt``.

В зависимости от типа данных и формата также может быть:

* Файл проекта QGIS ``data.qgs``, ArcMap ``data.mxd``, ArcGIS Pro ``data.aprx``  или Mapinfо ``data.wor``. Его можно сразу открыть в соответствующем ПО. Все данные уже добавлены в проект и стилизованы для отображения. 

   * Проекты для QGIS есть у всех продуктов при заказе форматов **Geopackage, Shape, GeoJSON**.
   * Проекты для ArcMap и ArcGIS Pro есть у всех продуктов при заказе форматов **Geodatabase, Shape**.
   * Проект для Mapinfo есть только у продукта base/osm при заказе формата **Mapinfo TAB**.

* Папка с иконками ``svg``. Эта папка включается для данных, использующих векторные маркеры в формате SVG. В стилях слоёв задан относительный путь к папке.



.. _ngdata_attr_osm:

Описание атрибутов выгрузок OpenStreetMap
-------------------------------------------

Обычно в ГИС данные организованы так, что имеется несколько слоёв, каждый с одним типом геометрии, и с одним набором атрибутов. В проекте Openstreetmap организация данных другая: есть одна общая база данных со всеми геометриями, ссылающимися друг на друга, и у каждого объекта имеются теги - пары «ключ-значение». Пользователи могут придумывать свои ключи, но общеупотребимые прописаны в wiki.openstreetmap.org. В выгрузках от NextGIS общеупотребительные объекты разделены по слоям, и для них взяты самые важные атрибуты.

* `Описание атрибутов в виде таблицы <https://docs.google.com/spreadsheets/d/1hW34n58AEQlu9eYsPUe_K2Kj1NZq5FCqlW6iSNSgcNg/edit?usp=sharing>`_

* Оригинальные описания тегов OSM в `вики Openstreetmap <https://wiki.openstreetmap.org/wiki/RU:Map_Features>`_

.. _ngdata_attr_other:

Описание атрибутов других выгрузок
-----------------------------------

* `Рельеф <https://docs.google.com/spreadsheets/d/1BcuWXMnwpwv0HIao3wAumgpqGsgfAzLc5yaOOCTeYBc/pubhtml>`_
* `Застройка AI <https://docs.google.com/spreadsheets/d/e/2PACX-1vS9EG8OMqxvcPemo-IMWQi_enrZij710YvKPmk3si5lQS_-sA5wCNj4waXefq0zvoouerktx0wrAlNW/pubhtml>`_
* `Дороги AI <https://docs.google.com/spreadsheets/d/e/2PACX-1vSx74nB_TPHRYNZTBFSRK5eEi_oxEBFCShT30VRYmk_sisD4qVcwRb-5F_IWiP2x-0pRGFWH8piHnWC/pubhtml>`_
* `Overture <https://docs.google.com/spreadsheets/d/e/2PACX-1vRJd2RsUimlo1GegSpnJScUdi0kImAJYumnWwbqyb6B2JWMwT9BAyIcIybsqQEBqSllCSNWviGJI9fC/pubhtml?gid=0&single=true>`_
* `Ландшафты <https://docs.google.com/spreadsheets/d/e/2PACX-1vRFm3v9NE3x62gAJ2fxMg-zn_i4lJHgplLJk6u_EeAl4G5VAWU095yFc7-omUIjjDkhdeAHrzkQ_em1/pubhtml>`_
* Космосъёмка - трёхканальное цветное изображение в формате RGB, других атрибутов не имеет
* `Реформа ЖКХ <https://docs.google.com/spreadsheets/d/e/2PACX-1vS32AGvxMh3_Yxuq_duKTIzQFfrJ88iEBciyn8ruhgGxAmyj2bcksH6JfoOs5p13YfZhPXAEqzRa783/pubhtml>`_
* `ООПТ <https://docs.google.com/spreadsheets/d/e/2PACX-1vQ11744S-kcUBR9gTOGv8ylhTVn2iEQzGA6m9dM0cEaKNEc0-CCm7fZTUPeftUeoms1cCf4uc7e3pjF/pubhtml>`_
* `Роснедра <https://docs.google.com/spreadsheets/d/e/2PACX-1vTDwgzllu93JNaL60BYHyTrirCqUigFwKYatMosvABIr8rVVHfmvHAaAy0D2gXFOw1Qcl2A2RN4O374/pubhtml>`_
* `Наследие <https://docs.google.com/spreadsheets/d/e/2PACX-1vRugZizn-rKnihRS6UYLulQUQbOBrUnkJQtiuGTWwwD39SmY6M5oLa94GD1Oww3eRf50_XM6atyP1Xw/pubhtml>`_
