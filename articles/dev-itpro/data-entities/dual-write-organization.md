---
title: Gerarchia organizzativa in Common Data Service
description: In questo argomento viene descritta l'integrazione dei dati organizzativi tra Finance and Operations e Common Data Service.
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
ms.openlocfilehash: ca2ac0f9dbb8544b12f23a271423a43b0e601272
ms.sourcegitcommit: 02c223b44ac7196df675afac61c6783f467d1983
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2019
ms.locfileid: "1789208"
---
## <a name="organization-hierarchy-in-common-data-service"></a>Gerarchia organizzativa in Common Data Service

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

Poiché Microsoft Dynamics 365 for Finance and Operations è un sistema finanziario, *organizzazione* è un concetto base e l'impostazione del sistema inizia con la configurazione di una gerarchia organizzativa. I dati finanziari e operazioni aziendali possono quindi essere tracciati a livello di organizzazione e anche a qualsiasi livello della gerarchia organizzativa.

Sebbene In Common Data Service non esiste il concetto di una gerarchia organizzativa, vi sono alcuni concetti isolati, come i ricavi di vendita totali. Come parte dell'integrazione con Common Data Service, , la struttura dati della gerarchia organizzativa viene aggiunta a Common Data Service.

## <a name="data-flow"></a>Flusso di dati

Un ecosistema aziendale composto da Finance and Operations e Common Data Service continuerà a avere una gerarchia organizzativa. Questa gerarchia organizzativa si basa su Finance and Operations, ma viene esposta in Common Data Service per scopi di informazione ed estendibilità. La figura di seguito mostra le informazioni di gerarchia organizzativa che vengono esposte in Common Data Service come flusso di dati unidirezionale da Finance and Operations a Common Data Service.

![Immagine dell'architettura](media/dual-write-data-flow.png)

## <a name="templates"></a>Modelli

Le mappe delle entità della gerarchia organizzativa sono disponibili per la sincronizzazione unidirezionale dei dati da Finance and Operations a Common Data Service.

[!include [banner](../includes/dual-write-symbols.md)]

## <a name="internal-organization-hierarchy-purpose"></a>Scopo gerarchia organizzativa interna

Questo modello consente la sincronizzazione unidirezionale dell'entità Scopo di gerarchia organizzativa da Finance and Operations a Dynamics 365 for Customer Engagement.

<!-- ![architecture image](media/dual-write-purpose.png) -->

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
HIERARCHYTYPE | \> | msdyn\_hierarchypurposetypename
HIERARCHYTYPE | \> | msdyn\_hierarchytype.msdyn\_name
HIERARCHYPURPOSE | \>\> | msdyn\_hierarchypurpose
IMMUTABLE | \>\> | msdyn\_immutable
SETASDEFAULT | \>\> | msdyn\_setasdefault

## <a name="internal-organization-hierarchy-type"></a>Tipo di gerarchia organizzativa interna

Questo modello consente la sincronizzazione unidirezionale dell'entità Tipo di gerarchia organizzativa da Finance and Operations a Customer Engagement.

<!-- ![architecture image](media/dual-write-type.png) -->

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
NOME | \> | msdyn\_name

## <a name="internal-organization-hierarchy"></a>Gerarchia organizzativa interna

Questo modello consente la sincronizzazione unidirezionale dell'entità Gerarchia organizzativa pubblicata da Finance and Operations a Customer Engagement.

<!-- ![architecture image](media/dual-write-organization.png) -->

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
VALIDTO | \> | msdyn\_validto
VALIDFROM | \> | msdyn\_validfrom
HIERARCHYTYPE | \> | msdyn\_hierarchytypename
PARENTORGANIZATIONPARTYNUMBER | \> | msdyn\_parentpartyid
CHILDORGANIZATIONPARTYNUMBER | \> | msdyn\_childpartyid
HIERARCHYTYPE | \> | msdyn\_hierarchytypeid.msdyn\_name
CHILDORGANIZATIONPARTYNUMBER | \> | msdyn\_childid.msdyn\_partynumber
PARENTORGANIZATIONPARTYNUMBER | \> | msdyn\_parentid.msdyn\_partynumber

## <a name="internal-organization"></a>Organizzazione interna

Le informazioni sull'organizzazione interna in Common Data Service vengono recuperate da due entità di Finance and Operations, **unità operativa** e **persone giuridiche**.

<!-- ![architecture image](media/dual-write-operating-unit.png) -->

<!-- ![architecture image](media/dual-write-legal-entities.png) -->

### <a name="operating-unit"></a>Unità operativa

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
LANGUAGEID | \> | msdyn\_languageid
NAMEALIAS | \> | msdyn\_namealias
NOME | \> | msdyn\_name
PARTYNUMBER | \> | msdyn\_partynumber
OPERATINGUNITTYPE | \>\> | msdyn\_type

### <a name="legal-entity"></a>Persona giuridica

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
NAMEALIAS | \> | msdyn\_namealias
LANGUAGEID | \> | msdyn\_languageid
NOME | \> | msdyn\_name
PARTYNUMBER | \> | msdyn\_partynumber
nessuno | \>\> | msdyn\_type
LEGALENTITYID | \> | msdyn\_companycode

## <a name="company"></a>Società

Fornisce la sincronizzazione bidirezionale delle informazioni sulla persona giuridica (società) tra Finance and Operations e Customer Engagement.

<!-- ![architecture image](media/dual-write-company.png) -->

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
NOME | = | cdm\_name
LEGALENTITYID | = | cdm\_companycode
