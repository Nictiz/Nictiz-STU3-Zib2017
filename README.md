# Nictiz-STU3-Zib2017
This repository contains HL7 FHIR STU3 compliant profiles. The FHIR profiles in this repository are based on the Release 2017 of the Dutch Clinical Building Blocks / Healthcare Information models (Dutch: [Zorginformatiebouwsteen or ZIB](https://zibs.nl/wiki/Zorginformatiebouwstenen "Zorginformatiebouwstenen")).

Among other things  these FHIR profiles cover the HCIMs/Zibs that are part of the [Basisgegevensset Zorg](https://www.registratieaandebron.nl/wat-is-registreren-aan-de-bron/de-kern-van-registreren-aan-de-bron/basisgegevensset/ "Basisgegevensset Zorg") (BGZ).

The Dutch National ICT institute in the Netherlands (Nictiz) maintains this repository and its contents. A number of contained core profiles have been developed under HL7 Netherlands responsability in cooperation with Nictiz and other parties. These profiles are marked slightly different in the name (nl-core-\*), the url (http://fhir.nl/*) and their publisher (HL7 Netherlands). Profiles by HL7 Netherlands are Patient, Organization, Practitioner, RelatedPerson, HealthcareService, EpisodeOfCare, Location, and datatypes Address and HumanName.

- - - -

## Git workflow

### Stable branches: v1.x and v2.x

Since 27th of January 2020 this project has two stable ("master") branches:
* stable-1.x (default on GitHub)
* stable-2.x

These branches correspond to the HL7 FHIR packages that Nictiz publishes.

*The current development branch will not be used anymore!*

### Branching strategy

Nictiz uses the following branching strategy for development:
* Releases correspond with the "stable-xxx" branches. These branches are only updated when there is a new release.
* Integrating of fixes and features is done on integration branches, called "release-xxx", where "xxx" is the version number of the upcoming release. Integration branches are created for each new release cycle and deleted after they are merged to the "stable-xxx" branches.
* Development of fixes and features is done:
	* Hotfixes (typo's etc.) are usually directly applied on the integration branch(es).
	* Larger issues are developed in topic branches. These issues are usually tracked in [BITS](https://bits.nictiz.nl) and the topic branches are called accordingly. Topic branches are merged into the integration branches when they are ready to be released. They are deleted after they are merged to all relevant integration branches.

The following illustration visualizes this workflow
```
stable-1.x
-----x-----------------x------------+--x-----------------
     |                 |            |  |
     | release-1.3.5   |            |  | release-1.3.6
     \----x---------+--|------------/  \-----+-----------
          |         |  |                     |
          | MM-1024 |  | MM-2048             |
          \---------/  \--\------------------/
                          |
stable-2.x                |
---------x----------------|----+--x----------------------
         |                |    |  |
         | release-2.0.1  |    |  | release-2.0.2
         \--x---------+---+----/  \----------------------
            |         |
            | MM-4096 |
            \---------/
```
Things to note:
* Both major versions have independent life cycles. For example, the release cycle for 2.0.1 starts and ends at a different point in time than the release cycle for 1.3.5.
* Topic branches may be branched from a release branch (MM-1024) or a stable branch (MM-2048), at the developer's discretion.
* Topic branches may be relevant for a single major version (MM-1024, MM-4096) or both major versions (MM-2048).
* Topic branches may have a life cycle independent from the releases (MM-2048).
