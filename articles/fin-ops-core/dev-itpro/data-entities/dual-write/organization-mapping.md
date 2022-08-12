---
title: Gerarchia organizzativa in Dataverse
description: In questo articolo viene descritta l'integrazione dei dati organizzativi tra le app per la finanza e le operazioni e Dataverse.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 2f900637855bee3e21916652a373c683e6bf1392
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2022
ms.locfileid: "9112020"
---
# <a name="organization-hierarchy-in-dataverse"></a>Gerarchia organizzativa in Dataverse

[!include [banner](../../includes/banner.md)]



Poiché Dynamics 365 Finance è un sistema finanziario, *organizzazione* è un concetto base e l'impostazione del sistema inizia con la configurazione di una gerarchia organizzativa. I dati finanziari aziendali possono quindi essere tracciati a livello di organizzazione e anche a qualsiasi livello della gerarchia organizzativa.

Sebbene In Dataverse non esiste il concetto di una gerarchia organizzativa, vi sono alcuni concetti isolati, come i ricavi di vendita totali. Come parte dell'integrazione con Dataverse, , la struttura dati della gerarchia organizzativa viene aggiunta a Dataverse.

## <a name="data-flow"></a>Flusso di dati

Un ecosistema aziendale composto dalle app per la finanza e le operazioni e Dataverse continuerà a avere una gerarchia organizzativa. Questa gerarchia organizzativa si basa sulle app per la finanza e le operazioni, ma viene esposta in Dataverse per scopi di informazione ed estendibilità. La figura di seguito mostra le informazioni di gerarchia organizzativa che vengono esposte in Dataverse come flusso di dati unidirezionale dalle app per la finanza e le operazioni a Dataverse.

![Immagine dell'architettura.](media/dual-write-data-flow.png)

Le mappe delle tabelle della gerarchia organizzativa sono disponibili per la sincronizzazione unidirezionale dei dati dalle app per la finanza e le operazioni a Dataverse.

## <a name="templates"></a>Modelli

Un'organizzazione è un gruppo di persone che collaborano per svolgere un processo aziendale o raggiungere un obiettivo. Le gerarchie organizzative rappresentano i rapporti tra le organizzazioni che fanno parte dell'azienda. È possibile definire i seguenti tipi di organizzazioni interne: persone giuridiche, unità operative e team. Come mostra la tabella seguente, viene creata una raccolta di mappe di tabelle per sincronizzare le informazioni su persone giuridiche, unità operativa, se relative gerarchie organizzative.

App Finanza e operazioni | App di interazione con i clienti     | Description
-----------------------|--------------------------------|---
[Persone giuridiche](mapping-reference.md#102) | cdm_companies | 
[Persone giuridiche](mapping-reference.md#142) | msdyn_internalorganizations |
[Unità operativa](mapping-reference.md#143) | msdyn_internalorganizations |
[Gerarchia organizzativa: pubblicata](mapping-reference.md#139) | msdyn_internalorganizationhierarchies | Questo modello consente la sincronizzazione unidirezionale di tabella gerarchia organizzativa pubblicata.
[Scopi gerarchia organizzativa](mapping-reference.md#140) | msdyn_internalorganizationhierarchypurposes | Questo modello consente la sincronizzazione unidirezionale di tabella scopo gerarchia organizzativa.
[Tipo di gerarchia organizzativa](mapping-reference.md#141) | msdyn_internalorganizationhierarchytypes | Questo modello consente la sincronizzazione unidirezionale di tabella tipo di gerarchia organizzativa.

## <a name="internal-organization"></a>Organizzazione interna

Le informazioni sull'organizzazione interna in Dataverse vengono recuperate da due tabelle, **unità operativa** e **persone giuridiche**.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

