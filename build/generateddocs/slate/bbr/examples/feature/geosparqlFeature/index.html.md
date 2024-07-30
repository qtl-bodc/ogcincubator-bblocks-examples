---
title: Feature with GeoSPARQL geometry (Schema)

language_tabs:
  - json: JSON
  - jsonld: JSON-LD
  - turtle: RDF/Turtle

toc_footers:
  - Version 1.0
  - <a href='#'>Feature with GeoSPARQL geometry</a>
  - <a href='https://blocks.ogc.org/register.html'>Building Blocks register</a>

search: true

code_clipboard: true

meta:
  - name: Feature with GeoSPARQL geometry (Schema)
---


# Feature with GeoSPARQL geometry `ogc.bbr.examples.feature.geosparqlFeature`

This example includes an uplift step to use a GeoSPARQL geometry in a GeoJSON object

<p class="status">
    <span data-rainbow-uri="http://www.opengis.net/def/status">Status</span>:
    <a href="http://www.opengis.net/def/status/under-development" target="_blank" data-rainbow-uri>Under development</a>
</p>

<aside class="success">
This building block is <strong><a href="https://github.com/ogcincubator/bblocks-examples/blob/master/build/tests/bbr/examples/feature/geosparqlFeature/" target="_blank">valid</a></strong>
</aside>

# Examples

## Sample feature



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

<blockquote class="lang-specific json">
  <p class="example-links">
    <a target="_blank" href="https://ogcincubator.github.io/bblocks-examples/build/tests/bbr/examples/feature/geosparqlFeature/example_1_1.json">Open in new window</a>
    <a target="_blank" href="https://avillar.github.io/TreedocViewer/?dataParser=json&amp;dataUrl=https%3A%2F%2Fogcincubator.github.io%2Fbblocks-examples%2Fbuild%2Ftests%2Fbbr%2Fexamples%2Ffeature%2FgeosparqlFeature%2Fexample_1_1.json&amp;expand=2&amp;option=%7B%22showTable%22%3A+false%7D">View on JSON Viewer</a></p>
</blockquote>




```jsonld
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
        40.156709946862875
      ]
    ]
  },
  "properties": {
    "myProp": "Mandatory property example"
  },
  "@context": "https://ogcincubator.github.io/bblocks-examples/build/annotated/bbr/examples/feature/geosparqlFeature/context.jsonld"
}
```

<blockquote class="lang-specific jsonld">
  <p class="example-links">
    <a target="_blank" href="https://ogcincubator.github.io/bblocks-examples/build/tests/bbr/examples/feature/geosparqlFeature/example_1_1.jsonld">Open in new window</a>
    <a target="_blank" href="https://json-ld.org/playground/#json-ld=https%3A%2F%2Fogcincubator.github.io%2Fbblocks-examples%2Fbuild%2Ftests%2Fbbr%2Fexamples%2Ffeature%2FgeosparqlFeature%2Fexample_1_1.jsonld">View on JSON-LD Playground</a>
</blockquote>




```turtle
@prefix geo: <http://www.opengis.net/ont/geosparql#> .
@prefix geojson: <https://purl.org/geojson/vocab#> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .

<http://example.com/features/f1> a geojson:Feature ;
    geo:hasGeometry [ geo:asGeoJson "{\"coordinates\":[[-111.67183507997295,40.056709946862874],[-111.71,40.156709946862875]],\"type\":\"LineString\"}"^^geo:geoJSONLiteral ] ;
    geojson:geometry "{\"coordinates\":[[-111.67183507997295,40.056709946862874],[-111.71,40.156709946862875]],\"type\":\"LineString\"}"^^rdf:JSON .


```

<blockquote class="lang-specific turtle">
  <p class="example-links">
    <a target="_blank" href="https://ogcincubator.github.io/bblocks-examples/build/tests/bbr/examples/feature/geosparqlFeature/example_1_1.ttl">Open in new window</a>
</blockquote>



# JSON Schema

```yaml--schema
allOf:
- $ref: https://opengeospatial.github.io/bblocks/annotated-schemas/geo/features/feature/schema.yaml
- properties:
    geometry:
      type: object
      x-jsonld-id: https://purl.org/geojson/vocab#geometry
      x-jsonld-type: '@json'
x-jsonld-prefixes:
  geojson: https://purl.org/geojson/vocab#

```

> <a target="_blank" href="https://avillar.github.io/TreedocViewer/?dataParser=yaml&amp;dataUrl=https%3A%2F%2Fogcincubator.github.io%2Fbblocks-examples%2Fbuild%2Fannotated%2Fbbr%2Fexamples%2Ffeature%2FgeosparqlFeature%2Fschema.yaml&amp;expand=2&amp;option=%7B%22showTable%22%3A+false%7D">View on YAML Viewer</a>

Links to the schema:

* YAML version: <a href="https://ogcincubator.github.io/bblocks-examples/build/annotated/bbr/examples/feature/geosparqlFeature/schema.yaml" target="_blank">https://ogcincubator.github.io/bblocks-examples/build/annotated/bbr/examples/feature/geosparqlFeature/schema.yaml</a>
* JSON version: <a href="https://ogcincubator.github.io/bblocks-examples/build/annotated/bbr/examples/feature/geosparqlFeature/schema.json" target="_blank">https://ogcincubator.github.io/bblocks-examples/build/annotated/bbr/examples/feature/geosparqlFeature/schema.json</a>


# JSON-LD Context

```json--ldContext
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
    "geojson": "https://purl.org/geojson/vocab#",
    "rdfs": "http://www.w3.org/2000/01/rdf-schema#",
    "oa": "http://www.w3.org/ns/oa#",
    "dct": "http://purl.org/dc/terms/",
    "@version": 1.1
  }
}
```

> <a target="_blank" href="https://json-ld.org/playground/#json-ld=https%3A%2F%2Fogcincubator.github.io%2Fbblocks-examples%2Fbuild%2Fannotated%2Fbbr%2Fexamples%2Ffeature%2FgeosparqlFeature%2Fcontext.jsonld">View on JSON-LD Playground</a>

You can find the full JSON-LD context here:
<a href="https://ogcincubator.github.io/bblocks-examples/build/annotated/bbr/examples/feature/geosparqlFeature/context.jsonld" target="_blank">https://ogcincubator.github.io/bblocks-examples/build/annotated/bbr/examples/feature/geosparqlFeature/context.jsonld</a>

# For developers

The source code for this Building Block can be found in the following repository:

* URL: <a href="https://github.com/ogcincubator/bblocks-examples" target="_blank">https://github.com/ogcincubator/bblocks-examples</a>
* Path:
<code><a href="https://github.com/ogcincubator/bblocks-examples/blob/HEAD/_sources/feature/geosparqlFeature" target="_blank">_sources/feature/geosparqlFeature</a></code>

