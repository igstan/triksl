## Run Locally

Make sure you're in the **maps** directory and then start a simple Python
server using:

```
$ python3 -m http.server 8000
```

Now go to: http://localhost:8000.

## Conversion Commands

```bash
ogr2ogr \
  -f GeoJSON \
  -where "ADM0_A3 IN ('ROU')" \
  subunits.json \
  ne_10m_admin_1_states_provinces/ne_10m_admin_1_states_provinces.shp
  ne_10m_admin_0_map_subunits/ne_10m_admin_0_map_subunits.shp

ogr2ogr \
  -f GeoJSON \
  -where "ISO_A2 = 'RO' AND FEATURECLA = 'Admin-1 capital'" \
  places.json \
  ne_10m_populated_places/ne_10m_populated_places.shp

topojson \
  --id-property name \
  -p name=NAME \
  -p name \
  -o romania.json \
  subunits.json \
  places.json
```

## Resources

 - [Let’s Make a Map][0]
 - [Making a map of Germany with topojson][1]

[0]: http://bost.ocks.org/mike/map/
[1]: http://milkator.wordpress.com/2013/02/25/making-a-map-of-germany-with-topojson/
