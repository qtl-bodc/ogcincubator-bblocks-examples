
# GeoJSON transformed to GeoSPARQL geometry (Schema)

`ogc.bbr.examples.feature.geosparqlFeature` *v1.0*

This example includes an uplift step to use a GeoSPARQL geometry in a GeoJSON object

[*Status*](http://www.opengis.net/def/status): Under development

## Examples

### Sample feature
#### json
```json
{
  "id": "f1",
  "type": "Feature",
  "geometry": {
    "type": "LineString",
    "coordinates": [
      [
        -111.67183507997295,
        40.056709946862874
      ],
      [
        -111.71,
        40.156709946862874
      ]
    ]
  },
  "properties": {
    "myProp": "Mandatory property example"
  }
}

```

#### jsonld
```jsonld
{
  "@context": "https://qtl-bodc.github.io/ogcincubator-bblocks-examples/build/annotated/bbr/examples/feature/geosparqlFeature/context.jsonld",
  "id": "f1",
  "type": "Feature",
  "geometry": {
    "type": "LineString",
    "coordinates": [
      [
        -111.67183507997295,
        40.056709946862874
      ],
      [
        -111.71,
        40.156709946862875
      ]
    ]
  },
  "properties": {
    "myProp": "Mandatory property example"
  }
}
```

#### ttl
```ttl
@prefix geo: <http://www.opengis.net/ont/geosparql#> .
@prefix geojson: <https://purl.org/geojson/vocab#> .
@prefix ns1: <http://example.org/myModel/> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .

<http://example.com/features/f1> a geojson:Feature ;
    ns1:myProp "Mandatory property example" ;
    geo:hasGeometry [ geo:asGeoJson "{\"coordinates\":[[-111.67183507997295,40.056709946862874],[-111.71,40.156709946862875]],\"type\":\"LineString\"}"^^geo:geoJSONLiteral ] ;
    geojson:geometry "{\"coordinates\":[[-111.67183507997295,40.056709946862874],[-111.71,40.156709946862875]],\"type\":\"LineString\"}"^^rdf:JSON .


```

## Schema

```yaml
allOf:
- $ref: https://opengeospatial.github.io/bblocks/annotated-schemas/geo/features/feature/schema.yaml
- properties:
    geometry:
      type: object
      x-jsonld-id: https://purl.org/geojson/vocab#geometry
      x-jsonld-type: '@json'
    properties:
      $ref: https://qtl-bodc.github.io/ogcincubator-bblocks-examples/build/annotated/bbr/examples/feature/propertySet/schema.yaml
x-jsonld-prefixes:
  geojson: https://purl.org/geojson/vocab#

```

Links to the schema:

* YAML version: [schema.yaml](https://qtl-bodc.github.io/ogcincubator-bblocks-examples/build/annotated/bbr/examples/feature/geosparqlFeature/schema.json)
* JSON version: [schema.json](https://qtl-bodc.github.io/ogcincubator-bblocks-examples/build/annotated/bbr/examples/feature/geosparqlFeature/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "type": "@type",
    "id": "@id",
    "properties": "@nest",
    "geometry": {
      "@context": {
        "coordinates": {
          "@container": "@list",
          "@id": "geojson:coordinates"
        }
      },
      "@id": "geojson:geometry",
      "@type": "@json"
    },
    "bbox": {
      "@container": "@list",
      "@id": "geojson:bbox"
    },
    "Feature": "geojson:Feature",
    "FeatureCollection": "geojson:FeatureCollection",
    "GeometryCollection": "geojson:GeometryCollection",
    "LineString": "geojson:LineString",
    "MultiLineString": "geojson:MultiLineString",
    "MultiPoint": "geojson:MultiPoint",
    "MultiPolygon": "geojson:MultiPolygon",
    "Point": "geojson:Point",
    "Polygon": "geojson:Polygon",
    "features": {
      "@container": "@set",
      "@id": "geojson:features"
    },
    "links": {
      "@context": {
        "href": {
          "@type": "@id",
          "@id": "oa:hasTarget"
        },
        "rel": {
          "@context": {
            "@base": "http://www.iana.org/assignments/relation/"
          },
          "@id": "http://www.iana.org/assignments/relation",
          "@type": "@id"
        },
        "type": "dct:type",
        "hreflang": "dct:language",
        "title": "rdfs:label",
        "length": "dct:extent"
      },
      "@id": "rdfs:seeAlso"
    },
    "myProp": "http://example.org/myModel/myProp",
    "geojson": "https://purl.org/geojson/vocab#",
    "rdfs": "http://www.w3.org/2000/01/rdf-schema#",
    "oa": "http://www.w3.org/ns/oa#",
    "dct": "http://purl.org/dc/terms/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://qtl-bodc.github.io/ogcincubator-bblocks-examples/build/annotated/bbr/examples/feature/geosparqlFeature/context.jsonld)


# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/qtl-bodc/ogcincubator-bblocks-examples](https://github.com/qtl-bodc/ogcincubator-bblocks-examples)
* Path: `_sources/feature/geosparqlFeature`

