# Aggregator Data Rights

| Status        | (Proposed / Accepted / Implemented / Obsolete)       |
:-------------- |:---------------------------------------------------- |
| **Author(s)** | @dgershman  |
| **Updated**   | 2024-09-17                                        |

## Objective

There may be cases where BMLT-enabled applications consume data from the aggregator.  When the aggregator ingests data it uses it's own primary key mechanism.  Multiple root servers could have the same original or source id, also known as collisions.  There may be cases, when referencing the original ID (also known as `id_bigint`), may be useful.  

## Motivation

This will allow for more interoperability between applications in order to further integrate systems.  When referencing a meeting it may be helpful to know whether or not the meeting is owned or accessible by a service body, since the data rights may not be owned by those that display it.  

## Design Proposal

When referencing the meeting ID, also reference the root server.  The application receiving this data must know ahead of time which root server (which is usually does) and service bodies it has rights over.  That application should handle the lookups to determine if it has the data rights over that meeting and deal with it appropriately.  If there are no data rights, it should provide a link or a redirect to the service body that has the rights over it.  Referencing the `url` field in `?switcher=GetServiceBodies`, would allow for this capability, however only 45% of service bodies are using it.  (ref: https://codepen.io/radius314/pen/JjQQvLW)

## Detailed Design

On Hold

## Questions and Discussion Topics

1. Does there need to be clarifications?
2. Other approaches?