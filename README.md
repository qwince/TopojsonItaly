Topojson of Italy
-----------------

Shapefile source: http://www.istat.it/it/archivio/24613

This is the procedure to get the topojson file

Convert shapefile to geojson, s_srs defines the input projection, t_srs defines the output projection to the EPSG code 4326 (http://spatialreference.org/ref/epsg/4326/)
see also http://www.gdal.org/ogr2ogr.html

    ogr2ogr -f GeoJSON -s_srs reg2011_g.prj -t_srs EPSG:4326 sub.json reg2011_g.shp

Converts geojson to topojson
(see https://github.com/mbostock/topojson/wiki/Command-Line-Reference)
    
    topojson -p nome_pro=NOME_PRO --id-property NOME_PRO -s 0.00000001 -o ita.json sub.json

Beautify the topojson file (not for the web)

    js-beautify -f ita.json -o ita_beauty.json
