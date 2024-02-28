---
title: External Schema (Smart Data Models) (Schema)

language_tabs:
  - json: JSON
  - jsonld: JSON-LD
  - turtle: RDF/Turtle

toc_footers:
  - Version 1.0
  - <a href='#'>External Schema (Smart Data Models)</a>
  - <a href='https://blocks.ogc.org/register.html'>Building Blocks register</a>

search: true

code_clipboard: true

meta:
  - name: External Schema (Smart Data Models) (Schema)
---


# External Schema (Smart Data Models) `ogc.bbr.examples.feature.externalSchema`

This examples shows a simple customisation for OGC API Feature using an externally defined domain schema.

<p class="status">
    <span data-rainbow-uri="http://www.opengis.net/def/status">Status</span>:
    <a href="http://www.opengis.net/def/status/under-development" target="_blank" data-rainbow-uri>Under development</a>
</p>

<aside class="success">
This building block is <strong><a href="https://github.com/ogcincubator/bblocks-examples/blob/master/build/tests/bbr/examples/feature/externalSchema/" target="_blank">valid</a></strong>
</aside>

# Description

## Feature Type based on a published schema

This example shows how an existing schema can be used to define a payload for a container model such as the OGC API Features feature schema.

This particular example uses a schema defined in another message-oriented environment, and **highlights an existing practice of using JSON-LD contexts defined for components.**

The OGC Building Blocks uses the same approach, with the added capabilities around example validation and mechanisms composition into other structures with transparent dependencies.



# Examples

## GeoJSON - specialisation example.



```json
{
  "id": "f1",
  "type": "Feature",
  "geometry": {
    "type": "Point",
    "coordinates": [
      59.354444,
      17.939722
    ]
  },
  "properties": {
    "id": "urn:ngsi-ld:AirportFacility:id:IUXP:30337114",
    "type": "AirportFacility",
    "IataCode": "BMA",
    "IcaoCode": "ESSB",
    "Name": "control"
  }
}

```

<blockquote class="lang-specific json">
  <p class="example-links">
    <a target="_blank" href="https://ogcincubator.github.io/bblocks-examples/build/tests/bbr/examples/feature/externalSchema/example_1_1.json">Open in new window</a>
    <a target="_blank" href="https://avillar.github.io/TreedocViewer/?dataParser=json&amp;dataUrl=https%3A%2F%2Fogcincubator.github.io%2Fbblocks-examples%2Fbuild%2Ftests%2Fbbr%2Fexamples%2Ffeature%2FexternalSchema%2Fexample_1_1.json&amp;expand=2&amp;option=%7B%22showTable%22%3A+false%7D">View on JSON Viewer</a></p>
</blockquote>




```jsonld
{
  "id": "f1",
  "type": "Feature",
  "geometry": {
    "type": "Point",
    "coordinates": [
      59.354444,
      17.939722
    ]
  },
  "properties": {
    "id": "urn:ngsi-ld:AirportFacility:id:IUXP:30337114",
    "type": "AirportFacility",
    "IataCode": "BMA",
    "IcaoCode": "ESSB",
    "Name": "control"
  },
  "@context": "https://ogcincubator.github.io/bblocks-examples/build/annotated/bbr/examples/feature/externalSchema/context.jsonld"
}
```

<blockquote class="lang-specific jsonld">
  <p class="example-links">
    <a target="_blank" href="https://ogcincubator.github.io/bblocks-examples/build/tests/bbr/examples/feature/externalSchema/example_1_1.jsonld">Open in new window</a>
    <a target="_blank" href="https://json-ld.org/playground/#json-ld=https%3A%2F%2Fogcincubator.github.io%2Fbblocks-examples%2Fbuild%2Ftests%2Fbbr%2Fexamples%2Ffeature%2FexternalSchema%2Fexample_1_1.jsonld">View on JSON-LD Playground</a>
</blockquote>




```turtle
@prefix geojson: <https://purl.org/geojson/vocab#> .
@prefix ns1: <https://smartdatamodels.org/dataModel.ACRIS/> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<http://example.com/features/f1> a geojson:Feature,
        ns1:AirportFacility ;
    geojson:geometry [ a geojson:Point ;
            geojson:coordinates ( 5.935444e+01 1.793972e+01 ) ] ;
    ns1:IataCode "BMA" ;
    ns1:IcaoCode "ESSB" ;
    ns1:Name "control" .


```

<blockquote class="lang-specific turtle">
  <p class="example-links">
    <a target="_blank" href="https://ogcincubator.github.io/bblocks-examples/build/tests/bbr/examples/feature/externalSchema/example_1_1.ttl">Open in new window</a>
</blockquote>



# JSON Schema

```yaml--schema
$schema: https://json-schema.org/draft/2020-12/schema
description: Example of a sinmple GeoJSON Feature specialisation
$defs:
  MyFeature:
    allOf:
    - $ref: https://opengeospatial.github.io/bblocks/annotated-schemas/geo/features/feature/schema.yaml
    - properties:
        properties:
          $ref: https://raw.githubusercontent.com/smart-data-models/dataModel.ACRIS/master/AirportFacility/schema.json
anyOf:
- $ref: '#/$defs/MyFeature'
x-jsonld-extra-terms:
  AirportElevation: https://smartdatamodels.org/dataModel.ACRIS/AirportElevation
  AirportElevationUnitOfMeasurement: https://smartdatamodels.org/dataModel.ACRIS/AirportElevationUnitOfMeasurement
  AirportFacility: https://smartdatamodels.org/dataModel.ACRIS/AirportFacility
  AirportLocation: https://smartdatamodels.org/dataModel.ACRIS/AirportLocation
  CheckpointAreaLocation: https://smartdatamodels.org/dataModel.ACRIS/CheckpointAreaLocation
  CheckpointFacility: https://smartdatamodels.org/dataModel.ACRIS/CheckpointFacility
  CheckpointFacilityOperatorParty: https://smartdatamodels.org/dataModel.ACRIS/CheckpointFacilityOperatorParty
  CheckpointFacilityType: https://smartdatamodels.org/dataModel.ACRIS/CheckpointFacilityType
  ClosingTime: https://smartdatamodels.org/dataModel.ACRIS/ClosingTime
  Code: https://smartdatamodels.org/dataModel.ACRIS/Code
  ConcourseFacility: https://smartdatamodels.org/dataModel.ACRIS/ConcourseFacility
  Description: https://smartdatamodels.org/dataModel.ACRIS/Description
  EndTime: https://smartdatamodels.org/dataModel.ACRIS/EndTime
  IataCode: https://smartdatamodels.org/dataModel.ACRIS/IataCode
  IcaoCode: https://smartdatamodels.org/dataModel.ACRIS/IcaoCode
  Identifier: https://smartdatamodels.org/dataModel.ACRIS/Identifier
  Latitude: https://smartdatamodels.org/dataModel.ACRIS/Latitude
  Longitude: https://smartdatamodels.org/dataModel.ACRIS/Longitude
  MeasurementDevice: https://smartdatamodels.org/dataModel.ACRIS/MeasurementDevice
  MeasurementDeviceLocation: https://smartdatamodels.org/dataModel.ACRIS/MeasurementDeviceLocation
  MeasurementTimePeriod: https://smartdatamodels.org/dataModel.ACRIS/MeasurementTimePeriod
  Name: https://smartdatamodels.org/dataModel.ACRIS/Name
  Occupancy: https://smartdatamodels.org/dataModel.ACRIS/Occupancy
  OpeningTime: https://smartdatamodels.org/dataModel.ACRIS/OpeningTime
  OperationTimePeriod: https://smartdatamodels.org/dataModel.ACRIS/OperationTimePeriod
  PassengerProcess: https://smartdatamodels.org/dataModel.ACRIS/PassengerProcess
  PassengerProcessType: https://smartdatamodels.org/dataModel.ACRIS/PassengerProcessType
  PassengerQueue: https://smartdatamodels.org/dataModel.ACRIS/PassengerQueue
  ProjectedWaitTime: https://smartdatamodels.org/dataModel.ACRIS/ProjectedWaitTime
  QueueLocation: https://smartdatamodels.org/dataModel.ACRIS/QueueLocation
  QueueMeasurement: https://smartdatamodels.org/dataModel.ACRIS/QueueMeasurement
  QueueStatus: https://smartdatamodels.org/dataModel.ACRIS/QueueStatus
  QueueType: https://smartdatamodels.org/dataModel.ACRIS/QueueType
  Srid: https://smartdatamodels.org/dataModel.ACRIS/Srid
  TerminalAreaLocation: https://smartdatamodels.org/dataModel.ACRIS/TerminalAreaLocation
  TerminalFacility: https://smartdatamodels.org/dataModel.ACRIS/TerminalFacility
  Throughput: https://smartdatamodels.org/dataModel.ACRIS/Throughput
  Value: https://smartdatamodels.org/dataModel.ACRIS/Value
  WaitTime: https://smartdatamodels.org/dataModel.ACRIS/WaitTime
  ZoneAreaLocation: https://smartdatamodels.org/dataModel.ACRIS/ZoneAreaLocation
  id: '@id'
  type: '@type'
x-jsonld-prefixes:
  ngsi-ld: https://uri.etsi.org/ngsi-ld/

```

> <a target="_blank" href="https://avillar.github.io/TreedocViewer/?dataParser=yaml&amp;dataUrl=https%3A%2F%2Fogcincubator.github.io%2Fbblocks-examples%2Fbuild%2Fannotated%2Fbbr%2Fexamples%2Ffeature%2FexternalSchema%2Fschema.yaml&amp;expand=2&amp;option=%7B%22showTable%22%3A+false%7D">View on YAML Viewer</a>

Links to the schema:

* YAML version: <a href="https://ogcincubator.github.io/bblocks-examples/build/annotated/bbr/examples/feature/externalSchema/schema.yaml" target="_blank">https://ogcincubator.github.io/bblocks-examples/build/annotated/bbr/examples/feature/externalSchema/schema.yaml</a>
* JSON version: <a href="https://ogcincubator.github.io/bblocks-examples/build/annotated/bbr/examples/feature/externalSchema/schema.json" target="_blank">https://ogcincubator.github.io/bblocks-examples/build/annotated/bbr/examples/feature/externalSchema/schema.json</a>


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
    "AirportElevation": "https://smartdatamodels.org/dataModel.ACRIS/AirportElevation",
    "AirportElevationUnitOfMeasurement": "https://smartdatamodels.org/dataModel.ACRIS/AirportElevationUnitOfMeasurement",
    "AirportFacility": "https://smartdatamodels.org/dataModel.ACRIS/AirportFacility",
    "AirportLocation": "https://smartdatamodels.org/dataModel.ACRIS/AirportLocation",
    "CheckpointAreaLocation": "https://smartdatamodels.org/dataModel.ACRIS/CheckpointAreaLocation",
    "CheckpointFacility": "https://smartdatamodels.org/dataModel.ACRIS/CheckpointFacility",
    "CheckpointFacilityOperatorParty": "https://smartdatamodels.org/dataModel.ACRIS/CheckpointFacilityOperatorParty",
    "CheckpointFacilityType": "https://smartdatamodels.org/dataModel.ACRIS/CheckpointFacilityType",
    "ClosingTime": "https://smartdatamodels.org/dataModel.ACRIS/ClosingTime",
    "Code": "https://smartdatamodels.org/dataModel.ACRIS/Code",
    "ConcourseFacility": "https://smartdatamodels.org/dataModel.ACRIS/ConcourseFacility",
    "Description": "https://smartdatamodels.org/dataModel.ACRIS/Description",
    "EndTime": "https://smartdatamodels.org/dataModel.ACRIS/EndTime",
    "IataCode": "https://smartdatamodels.org/dataModel.ACRIS/IataCode",
    "IcaoCode": "https://smartdatamodels.org/dataModel.ACRIS/IcaoCode",
    "Identifier": "https://smartdatamodels.org/dataModel.ACRIS/Identifier",
    "Latitude": "https://smartdatamodels.org/dataModel.ACRIS/Latitude",
    "Longitude": "https://smartdatamodels.org/dataModel.ACRIS/Longitude",
    "MeasurementDevice": "https://smartdatamodels.org/dataModel.ACRIS/MeasurementDevice",
    "MeasurementDeviceLocation": "https://smartdatamodels.org/dataModel.ACRIS/MeasurementDeviceLocation",
    "MeasurementTimePeriod": "https://smartdatamodels.org/dataModel.ACRIS/MeasurementTimePeriod",
    "Name": "https://smartdatamodels.org/dataModel.ACRIS/Name",
    "Occupancy": "https://smartdatamodels.org/dataModel.ACRIS/Occupancy",
    "OpeningTime": "https://smartdatamodels.org/dataModel.ACRIS/OpeningTime",
    "OperationTimePeriod": "https://smartdatamodels.org/dataModel.ACRIS/OperationTimePeriod",
    "PassengerProcess": "https://smartdatamodels.org/dataModel.ACRIS/PassengerProcess",
    "PassengerProcessType": "https://smartdatamodels.org/dataModel.ACRIS/PassengerProcessType",
    "PassengerQueue": "https://smartdatamodels.org/dataModel.ACRIS/PassengerQueue",
    "ProjectedWaitTime": "https://smartdatamodels.org/dataModel.ACRIS/ProjectedWaitTime",
    "QueueLocation": "https://smartdatamodels.org/dataModel.ACRIS/QueueLocation",
    "QueueMeasurement": "https://smartdatamodels.org/dataModel.ACRIS/QueueMeasurement",
    "QueueStatus": "https://smartdatamodels.org/dataModel.ACRIS/QueueStatus",
    "QueueType": "https://smartdatamodels.org/dataModel.ACRIS/QueueType",
    "Srid": "https://smartdatamodels.org/dataModel.ACRIS/Srid",
    "TerminalAreaLocation": "https://smartdatamodels.org/dataModel.ACRIS/TerminalAreaLocation",
    "TerminalFacility": "https://smartdatamodels.org/dataModel.ACRIS/TerminalFacility",
    "Throughput": "https://smartdatamodels.org/dataModel.ACRIS/Throughput",
    "Value": "https://smartdatamodels.org/dataModel.ACRIS/Value",
    "WaitTime": "https://smartdatamodels.org/dataModel.ACRIS/WaitTime",
    "ZoneAreaLocation": "https://smartdatamodels.org/dataModel.ACRIS/ZoneAreaLocation",
    "geojson": "https://purl.org/geojson/vocab#",
    "rdfs": "http://www.w3.org/2000/01/rdf-schema#",
    "oa": "http://www.w3.org/ns/oa#",
    "dct": "http://purl.org/dc/terms/",
    "ngsi-ld": "https://uri.etsi.org/ngsi-ld/",
    "@version": 1.1
  }
}
```

> <a target="_blank" href="https://json-ld.org/playground/#json-ld=https%3A%2F%2Fogcincubator.github.io%2Fbblocks-examples%2Fbuild%2Fannotated%2Fbbr%2Fexamples%2Ffeature%2FexternalSchema%2Fcontext.jsonld">View on JSON-LD Playground</a>

You can find the full JSON-LD context here:
<a href="https://ogcincubator.github.io/bblocks-examples/build/annotated/bbr/examples/feature/externalSchema/context.jsonld" target="_blank">https://ogcincubator.github.io/bblocks-examples/build/annotated/bbr/examples/feature/externalSchema/context.jsonld</a>

# References

* [OGC API - Features, Part 1, 7.16.2: Feature Response](https://docs.ogc.org/is/17-069r3/17-069r3.html#_response_7)
* [Smart Data models](https://smartdatamodels.org/)
* [Smart Data Model: Airport Facility](https://github.com/smart-data-models/dataModel.ACRIS/tree/master/AirportFacility)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: <a href="https://github.com/ogcincubator/bblocks-examples" target="_blank">https://github.com/ogcincubator/bblocks-examples</a>
* Path:
<code><a href="https://github.com/ogcincubator/bblocks-examples/blob/HEAD/_sources/feature/externalSchema" target="_blank">_sources/feature/externalSchema</a></code>

