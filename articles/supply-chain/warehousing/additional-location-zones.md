---
title: Zone ubicazione aggiuntive
description: Questo articolo offre una panoramica delle nuove zone di ubicazione aggiunte a Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
ms.date: 08/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocationBuild, WHSZone
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 819330e0f6e6cd419da441f919d68ff996b6475c
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2022
ms.locfileid: "9336517"
---
# <a name="additional-location-zones"></a>Zone ubicazione aggiuntive

[!include [banner](../includes/banner.md)]

Tre nuovi campi di zona sono disponibili in Microsoft Dynamics 365 Supply Chain Management. I responsabili del magazzino possono usarli per definire ulteriori layout o organizzazioni di magazzino. I nuovi campi di zona possono essere impostati manualmente o utilizzando la procedura guidata **Impostazione ubicazione**. Possono essere utilizzati in qualsiasi query o filtro che utilizza la tabella Ubicazioni.

Non è richiesta alcuna configurazione aggiuntiva per utilizzare i campi della zona.

## <a name="turn-the-additional-location-zone-feature-on-or-off"></a>Attivare o disattivare la funzionalità della zona di ubicazione aggiuntiva

Per utilizzare questa funzionalità, è necessario attivarla per il sistema. A partire dalla versione 10.0.25 di Supply Chain Management, la funzionalità è attivata per impostazione predefinita. A partire dalla versione 10.0.29 di Supply Chain Management, la funzionalità è obbligatoria e non può essere disattivata. Se si sta eseguendo una versione precedente alla versione 10.0.29, gli amministratori possono attivare o disattivare questa funzionalità cercando la funzionalità *Zona ubicazione aggiuntive* nell'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="use-location-zones"></a>Utilizzare le zone di ubicazione

1. Vai a **Gestione magazzino \> Impostazioni \> Magazzino \> Impostazione guidata ubicazione**.
2. Imposta i valori seguenti:

    - Nel campo **Magazzino** selezionare _62_.
    - Nel campo **ID zona**, seleziona _FLOOR_.
    - Nel campo **Zona aggiuntiva 1**, seleziona _PICKZONE1_.
    - Nel campo **Zona aggiuntiva 2**, seleziona _WEBSHOP1_.
    - Nel campo **ID profilo di ubicazione**, seleziona _FLOOR_.

3. Seleziona la riga **Piano**.
4. Nel campo **Numero di origine**, immetti _1_. Nel campo **Numero di destinazione**, immetti _3_.
5. Seleziona la riga **Sezione**.
6. Nel campo **Numero di origine**, immetti _1_. Nel campo **Numero di destinazione**, immetti _5_.
7. Selezionare **Crea**.
8. Ricevi messaggi che indicano che sono state aggiunte nuove ubicazioni. Seleziona il pulsante **Mostra messaggi** per visualizzare i messaggi.
9. Vai a **Gestione magazzino \> Impostazione \> Magazzino \> Ubicazioni**. Le nuove ubicazioni vengono visualizzate nell'elenco e tutti i campi della zona sono disponibili (ovvero, il campo della zona esistente e i nuovi campi della zona aggiuntivi).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]