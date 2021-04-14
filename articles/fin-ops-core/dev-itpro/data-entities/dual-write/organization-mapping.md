---
title: Gerarchia organizzativa in Dataverse
description: In questo argomento viene descritta l'integrazione dei dati dell'organizzazione tra le app Finance and Operations e Dataverse.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 8b147c27b9309b1b3597f1194c415fbb2e2b7ad2
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750814"
---
# <a name="organization-hierarchy-in-dataverse"></a>Gerarchia organizzativa in Dataverse

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Poiché Dynamics 365 Finance è un sistema finanziario, *organizzazione* è un concetto base e l'impostazione del sistema inizia con la configurazione di una gerarchia organizzativa. I dati finanziari aziendali possono quindi essere tracciati a livello di organizzazione e anche a qualsiasi livello della gerarchia organizzativa.

Sebbene In Dataverse non esiste il concetto di una gerarchia organizzativa, vi sono alcuni concetti isolati, come i ricavi di vendita totali. Come parte dell'integrazione con Dataverse, , la struttura dati della gerarchia organizzativa viene aggiunta a Dataverse.

## <a name="data-flow"></a>Flusso di dati

Un ecosistema aziendale composto dalle app Finance and Operations e Dataverse continuerà a avere una gerarchia organizzativa. Questa gerarchia organizzativa si basa sulle app Finance and Operations, ma viene esposta in Dataverse per scopi di informazione ed estendibilità. La figura di seguito mostra le informazioni di gerarchia organizzativa che vengono esposte in Dataverse come flusso di dati unidirezionale dalle app Finance and Operations a Dataverse.

![Immagine dell'architettura](media/dual-write-data-flow.png)

Le mappe della tabella della gerarchia organizzativa sono disponibili per la sincronizzazione unidirezionale dei dati dalle Finance and Operations app a Dataverse.

## <a name="templates"></a>Modelli

Le informazioni di prodotto contengono tutte le informazioni sul prodotto e sulla relativa definizione, come le dimensioni prodotto o le dimensioni di tracciabilità e di immagazzinamento. Come mostrato nella tabella seguente, una raccolta di mappe della tabella viene creata per sincronizzare i prodotti e le informazioni correlate.

App di Finance and Operations | Altre app Dynamics 365 | Descrizione
-----------------------|--------------------------------|---
Scopi gerarchia organizzativa | msdyn_internalorganizationhierarchypurposes | Questo modello consente la sincronizzazione unidirezionale di tabella scopo gerarchia organizzativa.
Tipo di gerarchia organizzativa | msdyn_internalorganizationhierarchytypes | Questo modello consente la sincronizzazione unidirezionale di tabella tipo di gerarchia organizzativa.
Gerarchia organizzativa: pubblicata | msdyn_internalorganizationhierarchies | Questo modello consente la sincronizzazione unidirezionale di tabella gerarchia organizzativa pubblicata.
Unità operativa | msdyn_internalorganizations |
Persone giuridiche | msdyn_internalorganizations |
Persone giuridiche | cdm_companies | Fornisce la sincronizzazione bidirezionale delle informazioni della persona giuridica (società).

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Organization hierarchy purposes](includes/OrganizationHierarchyPurpose-msdyn-internalorganizationhierarchypurposes.md)]

[!include [Organization hierarchy type](includes/OrganizationHierarchyType-msdyn-internalorganizationhierarchytypes.md)]

[!include [Organization hierarchy - published](includes/OrganizationHierarchyPublished-msdyn-internalorganizationhierarchies.md)]

## <a name="internal-organization"></a>Organizzazione interna

Le informazioni sull'organizzazione interna in Dataverse vengono recuperate da due tabelle, **unità operativa** e **persone giuridiche**.

[!include [Operating unit](includes/OperatingUnit-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-Companies.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]