---
title: Gabarits de données structurées
layout: gabarits-doc
---

[![en](https://img.shields.io/badge/lang-en-blue.svg)](https://github.com/culturecreates/artsdata-data-model/blob/master/_gabarits-jsonld/README.md)
[![fr](https://img.shields.io/badge/lang-fr-green.svg)](https://github.com/culturecreates/artsdata-data-model/blob/master/_gabarits-jsonld/README.fr.md)

Gabarits de données structurées
============================================

Gabarits de données structurées au format JSON-LD s'appuyant sur le vocabulaire Schema.org.

Inspiré par le projet Gabarits de données structurées de [La danse sur les routes du Québec](https://github.com/a10s-ca/ladsr-ds/blob/main/README.md)

## Conventions

### Identification des valeurs à modifier dans le gabarit

Les gabarits sont rendus disponibles sous forme de fichier contenant des données au format JSON-LD.

Afin de faciliter la compréhension et l'utilisation, des notes explicatives ont été incluses à propos des valeurs attendues et du format dans lequel elles devraient être saisie. Ces notes ont été placées entre de doubles tirets en français et anglais. Par exemple:

```
"url": "--URL complète vers la page Web concernée : Full URL to the relevant webpage--"
```

Une fois le gabarit utilisé et rempli avec des données, il ne devrait plus contenir de doubles tirets. Par exemple:

```
"url": "https://placedesarts.com"
```

## Gabarit

Le gabarit _Événement_ est destiné à représenter les informations à propos d'événements uniques, c'est-à-dire un spectacle ayant une seule représentation. Si votre événement comporte une série de représentations d'un même spectacle, veuillez *ajouter* l'extension _Série d'événements_ au gabarit _Événement_ afin de décrire chaque représentation comme un ['subEvent'](https://schema.org/subEvent), puis changez le type de l'événement principal pour ['EventSeries'](https://schema.org/EventSeries).

- [Gabarit Événement](https://github.com/culturecreates/artsdata-data-model/blob/master/_gabarits-jsonld/Event/event.jsonld) : événement unique (avec une seule représentation).

- [Extension pour les Séries d'événements](https://github.com/culturecreates/artsdata-data-model/blob/master/_gabarits-jsonld/Event/event_series.jsonld) : extension du gabarit _Événement_ pour décrire chaque représentation d'un même spectacle.

## Détails sur certaines propriétés clés

### [_additionalType_](https://schema.org/additionalType)
Saisissez des types supplémentaires correspondant au type particulier de l’événement. Référez-vous au la [vocabulaire contrôlé Artsdata](http://kg.artsdata.ca/resource/ArtsdataEventTypes) pour identifier le ou les types les mieux appropriés parmi tous les types d'événements des arts de la scène. Vous pouvez ajouter autant de propriétés _additionalType_ que nécessaire pour bien décrire l'événement. En guise de valeur par défaut, nous recommandons le type [PerformingArtsEvent](http://kg.artsdata.ca/resource/PerformingArtsEvent), qui désigne « une œuvre des arts de la scène exécutée pour un public ».

### [_name_](https://schema.org/name)
Saisissez le titre de l’événement.

### [_url_](https://schema.org/url)
Saisissez l'URL de la page web de l'événement sur le site de l'organisateur. 
Dans le cas de séries de représentations, en plus de l'URL de la page web de la série, une URL distincte devrait être assignée à chaque représentation à l'aide de l'[Extension pour les Séries d'événements](https://github.com/culturecreates/artsdata-data-model/blob/master/_gabarits-jsonld/Event/event_series.jsonld). Si les différentes représentations ne disposent pas de leurs propres page web (en sus de la page de la série), il est tout de même possible de leur assigner des URL ajoutant des ancres # suivies de la date de chaque représentation.

### [_eventStatus_](https://schema.org/eventStatus)
Indiquez si un événement est [programmé](https://schema.org/EventScheduled) (avec date), [reporté](https://schema.org/EventPostponed) (date à confirmer), [reprogrammé](https://schema.org/EventRescheduled) (avec nouvelle date) ou [annulé](https://schema.org/EventCancelled).

### [_eventAttendanceMode_](https://schema.org/eventAttendanceMode)
Indiquez si un événement se produit [en personne](https://schema.org/OfflineEventAttendanceMode), [en ligne](https://schema.org/OnlineEventAttendanceMode), ou format [hybride](https://schema.org/MixedEventAttendanceMode).

### [_organizer_](https://schema.org/organizer)
Saisissez les informations identifiant et décrivant l'organisme qui est responsable de la présentation du spectacle. Il peut s'agir d'un organisme diffuseur ou d'une compagnie qui présente sa propre production. On peut ajouter plusieurs _organizer(s)_. Les entités décrites sous cette propriété sont généralement de @type [Organization](https://schema.org/Organization).

### [_performer_](https://schema.org/performer)
Saisissez les informations identifiant et décrivant la compagnie, le groupe ou la (des) personne(s) qui est(sont) responsable de l'exécution de la représentation. Il est possible d'ajouter plusieurs _performer(s)_. Les entités décrites sous cette propriété peuvent être de @type [Organization](https://schema.org/Organization), [PerformingGroup](https://schema.org/PerformingGroup) ou [Person](https://schema.org/Person). 

### [_location_](https://schema.org/location)
Saisissez les informations identifiant et décrivant l'endroit où est présenté l'événement. L'entité décrite sous la propriété _location_ peut être de @type [Place](https://schema.org/Place) (un lieu physique) ou de @type [VirtualLocation](https://schema.org/VirtualLocation) (un lieu virtuel).

### [_offers_](https://schema.org/offers)
Saisissez les informations à propos de la disponibilité des billets et de la page Web où l'on peut se les procurer.


