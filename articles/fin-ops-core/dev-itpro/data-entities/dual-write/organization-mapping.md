---
title: Gerarchia organizzativa in Common Data Service
description: In questo argomento viene descritta l'integrazione dei dati dell'organizzazione tra le app Finance and Operations e Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: fc5db8d04a2860df0c917816e2910c6fbda941ff
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "3173156"
---
# <a name="organization-hierarchy-in-common-data-service"></a>Gerarchia organizzativa in Common Data Service

[!include [banner](../../includes/banner.md)]



Poiché Dynamics 365 Finance è un sistema finanziario, *organizzazione* è un concetto base e l'impostazione del sistema inizia con la configurazione di una gerarchia organizzativa. I dati finanziari aziendali possono quindi essere tracciati a livello di organizzazione e anche a qualsiasi livello della gerarchia organizzativa.

Sebbene In Common Data Service non esiste il concetto di una gerarchia organizzativa, vi sono alcuni concetti isolati, come i ricavi di vendita totali. Come parte dell'integrazione con Common Data Service, , la struttura dati della gerarchia organizzativa viene aggiunta a Common Data Service.

## <a name="data-flow"></a>Flusso di dati

Un ecosistema aziendale composto dalle app Finance and Operations e Common Data Service continuerà a avere una gerarchia organizzativa. Questa gerarchia organizzativa si basa sulle app Finance and Operations, ma viene esposta in Common Data Service per scopi di informazione ed estendibilità. La figura di seguito mostra le informazioni di gerarchia organizzativa che vengono esposte in Common Data Service come flusso di dati unidirezionale dalle app Finance and Operations a Common Data Service.

![Immagine dell'architettura](media/dual-write-data-flow.png)

## <a name="templates"></a>Modelli

Le mappe delle entità della gerarchia organizzativa sono disponibili per la sincronizzazione unidirezionale dei dati dalle app Finance and Operations a Common Data Service.

## <a name="templates"></a>Modelli

Le informazioni di prodotto contengono tutte le informazioni sul prodotto e sulla relativa definizione, come le dimensioni prodotto o le dimensioni di tracciabilità e di immagazzinamento. Come mostrato nella tabella seguente, una raccolta di mappe di entità viene creata per sincronizzare i prodotti e le informazioni correlate.

App di Finance and Operations | Altre app Dynamics 365 | descrizione
-----------------------|--------------------------------|---
Scopi gerarchia organizzativa | msdyn_internalorganizationhierarchypurposes | Questo modello consente la sincronizzazione unidirezionale di entità scopo gerarchia organizzativa.
Tipo di gerarchia organizzativa | msdyn_internalorganizationhierarchytypes | Questo modello consente la sincronizzazione unidirezionale di entità tipo di gerarchia organizzativa.
Gerarchia organizzativa - pubblicata | msdyn_internalorganizationhierarchies | Questo modello consente la sincronizzazione unidirezionale di entità gerarchia organizzativa pubblicata.
Unità operativa | msdyn_internalorganizations | 
Persone giuridiche | msdyn_internalorganizations | 
Persone giuridiche | cdm_companies | Fornisce la sincronizzazione bidirezionale delle informazioni della persona giuridica (società).


[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Organization hierarchy purposes](includes/OrganizationHierarchyPurpose-msdyn-internalorganizationhierarchypurposes.md)]

[!include [Organization hierarchy type](includes/OrganizationHierarchyType-msdyn-internalorganizationhierarchytypes.md)]

[!include [Organization hierarchy - published](includes/OrganizationHierarchyPublished-msdyn-internalorganizationhierarchies.md)]

## <a name="internal-organization"></a>Organizzazione interna

Le informazioni sull'organizzazione interna in Common Data Service vengono recuperate da due entità, **unità operativa** e **persone giuridiche**.

[!include [Operating unit](includes/OperatingUnit-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-Companies.md)]

