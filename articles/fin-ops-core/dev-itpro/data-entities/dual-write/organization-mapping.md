---
title: Gerarchia organizzativa in Dataverse
description: In questo argomento viene descritta l'integrazione dei dati organizzativi tra le app per finanza e operazioni e Dataverse.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: afc1b5996667835c460f467526493380aa2d6403
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8062088"
---
# <a name="organization-hierarchy-in-dataverse"></a>Gerarchia organizzativa in Dataverse

[!include [banner](../../includes/banner.md)]



Poiché Dynamics 365 Finance è un sistema finanziario, *organizzazione* è un concetto base e l'impostazione del sistema inizia con la configurazione di una gerarchia organizzativa. I dati finanziari aziendali possono quindi essere tracciati a livello di organizzazione e anche a qualsiasi livello della gerarchia organizzativa.

Sebbene In Dataverse non esiste il concetto di una gerarchia organizzativa, vi sono alcuni concetti isolati, come i ricavi di vendita totali. Come parte dell'integrazione con Dataverse, , la struttura dati della gerarchia organizzativa viene aggiunta a Dataverse.

## <a name="data-flow"></a>Flusso di dati

Un ecosistema aziendale composto dalle app per finanza e operazioni e Dataverse continuerà a avere una gerarchia organizzativa. Questa gerarchia organizzativa si basa sulle app per finanza e operazioni, ma viene esposta in Dataverse per scopi di informazione ed estendibilità. La figura di seguito mostra le informazioni di gerarchia organizzativa che vengono esposte in Dataverse come flusso di dati unidirezionale dalle app per finanza e operazioni a Dataverse.

![Immagine dell'architettura.](media/dual-write-data-flow.png)

Le mappe delle tabelle della gerarchia organizzativa sono disponibili per la sincronizzazione unidirezionale dei dati dalle app per finanza e operazioni a Dataverse.

## <a name="templates"></a>Modelli

Le informazioni di prodotto contengono tutte le informazioni sul prodotto e sulla relativa definizione, come le dimensioni prodotto o le dimensioni di tracciabilità e di immagazzinamento. Come mostrato nella tabella seguente, una raccolta di mappe della tabella viene creata per sincronizzare i prodotti e le informazioni correlate.

App Finanza e operazioni | App di interazione con i clienti     | descrizione
-----------------------|--------------------------------|---
[Persone giuridiche](mapping-reference.md#102) | cdm_companies | Fornisce la sincronizzazione bidirezionale delle informazioni della persona giuridica (società).
[Persone giuridiche](mapping-reference.md#142) | msdyn_internalorganizations |
[Unità operativa](mapping-reference.md#143) | msdyn_internalorganizations |
[Gerarchia organizzativa: pubblicata](mapping-reference.md#139) | msdyn_internalorganizationhierarchies | Questo modello consente la sincronizzazione unidirezionale di tabella gerarchia organizzativa pubblicata.
[Scopi gerarchia organizzativa](mapping-reference.md#140) | msdyn_internalorganizationhierarchypurposes | Questo modello consente la sincronizzazione unidirezionale di tabella scopo gerarchia organizzativa.
[Tipo di gerarchia organizzativa](mapping-reference.md#141) | msdyn_internalorganizationhierarchytypes | Questo modello consente la sincronizzazione unidirezionale di tabella tipo di gerarchia organizzativa.

## <a name="internal-organization"></a>Organizzazione interna

Le informazioni sull'organizzazione interna in Dataverse vengono recuperate da due tabelle, **unità operativa** e **persone giuridiche**.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
