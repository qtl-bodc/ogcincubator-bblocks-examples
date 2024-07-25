---
title: Custom JSON-FG (lenient) Feature (Schema)

language_tabs:
  - json: JSON
  - jsonld: JSON-LD
  - turtle: RDF/Turtle

toc_footers:
  - Version 1.0
  - <a href='#'>Custom JSON-FG (lenient) Feature</a>
  - <a href='https://blocks.ogc.org/register.html'>Building Blocks register</a>

search: true

code_clipboard: true

meta:
  - name: Custom JSON-FG (lenient) Feature (Schema)
---


# Custom JSON-FG (lenient) Feature `ogc.bbr.examples.feature.geojsonFeatureFGLenient`

This example shows a simple customisation method for a JSON-FG (lenient) feature

<p class="status">
    <span data-rainbow-uri="http://www.opengis.net/def/status">Status</span>:
    <a href="http://www.opengis.net/def/status/under-development" target="_blank" data-rainbow-uri>Under development</a>
</p>

<aside class="success">
This building block is <strong><a href="https://github.com/ogcincubator/bblocks-examples/blob/master/build/tests/bbr/examples/feature/geojsonFeatureFGLenient/" target="_blank">valid</a></strong>
</aside>

# Description

## Custom Feature Type

This building block illustrates a typical "Feature Type" - where an object is modelled as a "Feature with geometry",
but has its own "native schema" - or "domain model". It uses JSON-FG (lenient) as its base.

This is an **interoperable** approach to defining a Feature, allowing re-use of a well-defined domain model.

i.e. the attributes (properties) are managed independently of the packaging container (Feature)

the **propertySet** building block referenced by this container may be used independently of the FeatureModel structure,
and is where semantic annotations are provided.

This building block **inherits** reusable semantic annotations for the Feature structure from a common library,
simplifying implementation. 




# Examples

## GeoJSON - specialisation example.



```json
{
  "id": "f1",
  "type": "Feature",
  "featureType": "app:building",
  "coordRefSys": "http://www.opengis.net/def/crs/EPSG/0/5555",
  "time": { "interval": ["2014-04-24T10:50:18Z", ".."] },
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
    <a target="_blank" href="https://ogcincubator.github.io/bblocks-examples/build/tests/bbr/examples/feature/geojsonFeatureFGLenient/example_1_1.json">Open in new window</a>
    <a target="_blank" href="https://avillar.github.io/TreedocViewer/?dataParser=json&amp;dataUrl=https%3A%2F%2Fogcincubator.github.io%2Fbblocks-examples%2Fbuild%2Ftests%2Fbbr%2Fexamples%2Ffeature%2FgeojsonFeatureFGLenient%2Fexample_1_1.json&amp;expand=2&amp;option=%7B%22showTable%22%3A+false%7D">View on JSON Viewer</a></p>
</blockquote>




```jsonld
{
  "id": "f1",
  "type": "Feature",
  "featureType": "app:building",
  "coordRefSys": "http://www.opengis.net/def/crs/EPSG/0/5555",
  "time": {
    "interval": [
      "2014-04-24T10:50:18Z",
      ".."
    ]
  },
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
  "@context": "https://ogcincubator.github.io/bblocks-examples/build/annotated/bbr/examples/feature/geojsonFeatureFGLenient/context.jsonld"
}
```

<blockquote class="lang-specific jsonld">
  <p class="example-links">
    <a target="_blank" href="https://ogcincubator.github.io/bblocks-examples/build/tests/bbr/examples/feature/geojsonFeatureFGLenient/example_1_1.jsonld">Open in new window</a>
    <a target="_blank" href="https://json-ld.org/playground/#json-ld=https%3A%2F%2Fogcincubator.github.io%2Fbblocks-examples%2Fbuild%2Ftests%2Fbbr%2Fexamples%2Ffeature%2FgeojsonFeatureFGLenient%2Fexample_1_1.jsonld">View on JSON-LD Playground</a>
</blockquote>




```turtle
@prefix dcterms: <http://purl.org/dc/terms/> .
@prefix geojson: <https://purl.org/geojson/vocab#> .
@prefix ns1: <http://www.opengis.net/def/glossary/term/> .
@prefix ns2: <http://example.org/myModel/> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix time: <http://www.w3.org/2006/time#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<http://example.com/features/f1> a <app:building>,
        geojson:Feature ;
    ns2:myProp "Mandatory property example" ;
    dcterms:time [ time:hasTime ( "2014-04-24T10:50:18Z" ".." ) ] ;
    ns1:CoordinateReferenceSystemCRS "http://www.opengis.net/def/crs/EPSG/0/5555" ;
    geojson:geometry [ a geojson:LineString ;
            geojson:coordinates ( ( -1.116718e+02 4.005671e+01 ) ( -1.1171e+02 4.015671e+01 ) ) ] .


```

<blockquote class="lang-specific turtle">
  <p class="example-links">
    <a target="_blank" href="https://ogcincubator.github.io/bblocks-examples/build/tests/bbr/examples/feature/geojsonFeatureFGLenient/example_1_1.ttl">Open in new window</a>
</blockquote>



# JSON Schema

```yaml--schema
$schema: https://json-schema.org/draft/2020-12/schema
description: Example of a sinmple GeoJSON Feature specialisation
allOf:
- $ref: https://opengeospatial.github.io/bblocks/annotated-schemas/geo/json-fg/feature-lenient/schema.yaml
- properties:
    properties:
      $ref: https://ogcincubator.github.io/bblocks-examples/build/annotated/bbr/examples/feature/propertySet/schema.yaml

```

> <a target="_blank" href="https://avillar.github.io/TreedocViewer/?dataParser=yaml&amp;dataUrl=https%3A%2F%2Fogcincubator.github.io%2Fbblocks-examples%2Fbuild%2Fannotated%2Fbbr%2Fexamples%2Ffeature%2FgeojsonFeatureFGLenient%2Fschema.yaml&amp;expand=2&amp;option=%7B%22showTable%22%3A+false%7D">View on YAML Viewer</a>

Links to the schema:

* YAML version: <a href="https://ogcincubator.github.io/bblocks-examples/build/annotated/bbr/examples/feature/geojsonFeatureFGLenient/schema.yaml" target="_blank">https://ogcincubator.github.io/bblocks-examples/build/annotated/bbr/examples/feature/geojsonFeatureFGLenient/schema.yaml</a>
* JSON version: <a href="https://ogcincubator.github.io/bblocks-examples/build/annotated/bbr/examples/feature/geojsonFeatureFGLenient/schema.json" target="_blank">https://ogcincubator.github.io/bblocks-examples/build/annotated/bbr/examples/feature/geojsonFeatureFGLenient/schema.json</a>


# JSON-LD Context

```json--ldContext
{
  "@context": {
    "type": "@type",
    "id": "@id",
    "properties": "@nest",
    "geometry": {
      "@context": {},
      "@id": "geojson:geometry"
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
    "featureType": "@type",
    "time": {
      "@context": {
        "date": {
          "@id": "owlTime:hasTime",
          "@type": "xsd:date"
        },
        "timestamp": {
          "@id": "owlTime:hasTime",
          "@type": "xsd:dateTime"
        },
        "interval": {
          "@id": "owlTime:hasTime",
          "@container": "@list"
        }
      },
      "@id": "dct:time"
    },
    "coordRefSys": "http://www.opengis.net/def/glossary/term/CoordinateReferenceSystemCRS",
    "place": "dct:spatial",
    "Polyhedron": "geojson:Polyhedron",
    "MultiPolyhedron": "geojson:MultiPolyhedron",
    "Prism": {
      "@id": "geojson:Prism",
      "@context": {
        "base": "geojson:prismBase",
        "lower": "geojson:prismLower",
        "upper": "geojson:prismUpper"
      }
    },
    "MultiPrism": {
      "@id": "geojson:MultiPrism",
      "@context": {
        "prisms": "geojson:prisms"
      }
    },
    "coordinates": {
      "@container": "@list",
      "@id": "geojson:coordinates"
    },
    "geometries": {
      "@id": "geojson:geometry",
      "@container": "@list"
    },
    "myProp": "http://example.org/myModel/myProp",
    "geojson": "https://purl.org/geojson/vocab#",
    "rdfs": "http://www.w3.org/2000/01/rdf-schema#",
    "oa": "http://www.w3.org/ns/oa#",
    "dct": "http://purl.org/dc/terms/",
    "owlTime": "http://www.w3.org/2006/time#",
    "xsd": "http://www.w3.org/2001/XMLSchema#",
    "@version": 1.1
  }
}
```

> <a target="_blank" href="https://json-ld.org/playground/#json-ld=https%3A%2F%2Fogcincubator.github.io%2Fbblocks-examples%2Fbuild%2Fannotated%2Fbbr%2Fexamples%2Ffeature%2FgeojsonFeatureFGLenient%2Fcontext.jsonld">View on JSON-LD Playground</a>

You can find the full JSON-LD context here:
<a href="https://ogcincubator.github.io/bblocks-examples/build/annotated/bbr/examples/feature/geojsonFeatureFGLenient/context.jsonld" target="_blank">https://ogcincubator.github.io/bblocks-examples/build/annotated/bbr/examples/feature/geojsonFeatureFGLenient/context.jsonld</a>

# Validation

## SHACL Shapes

The following sets of SHACL shapes are used for validating this building block:

* Observation Properties <small><code>ogc.sosa.properties.observation</code></small>
  * [https://opengeospatial.github.io/ogcapi-sosa/_sources/properties/observation/rules.shacl](https://opengeospatial.github.io/ogcapi-sosa/_sources/properties/observation/rules.shacl)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: <a href="https://github.com/ogcincubator/bblocks-examples" target="_blank">https://github.com/ogcincubator/bblocks-examples</a>
* Path:
<code><a href="https://github.com/ogcincubator/bblocks-examples/blob/HEAD/_sources/feature/geojsonFeatureFGLenient" target="_blank">_sources/feature/geojsonFeatureFGLenient</a></code>

