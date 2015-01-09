Topojson of Italy
-----------------

Shapefile source: http://www.istat.it/it/archivio/24613

This is the procedure to get the topojson file

Convert shapefile to geojson, s_srs defines the input projection, t_srs defines the output projection to the EPSG code 4326 (http://spatialreference.org/ref/epsg/4326/)
see also http://www.gdal.org/ogr2ogr.html

    ogr2ogr -f GeoJSON -s_srs prov2011_g.prj -t_srs EPSG:4326 sub.json prov2011_g.shp

Converts geojson to topojson
(see https://github.com/mbostock/topojson/wiki/Command-Line-Reference)
    
    topojson -p nome_pro=NOME_PRO -p nome_pro --id-property NOME_PRO -s 0.00000001 -o itx.json sub.json

Beautify the topojson file (not for the web)

    js-beautify -f it.json -o it_beauty.json
