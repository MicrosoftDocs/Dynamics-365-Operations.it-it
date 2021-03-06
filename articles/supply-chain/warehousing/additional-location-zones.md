---
title: Zone ubicazione aggiuntive
description: Questo argomento offre una panoramica delle nuove zone di ubicazione aggiunte a Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
ms.date: 07/01/2020
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
ms.openlocfilehash: ee6e0b824ff16bf757159da5198a4215f4f5d121
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808944"
---
# <a name="additional-location-zones"></a>Zone ubicazione aggiuntive

[!include [banner](../includes/banner.md)]

Tre nuovi campi di zona sono disponibili in Microsoft Dynamics 365 Supply Chain Management. I responsabili del magazzino possono usarli per definire ulteriori layout o organizzazioni di magazzino. I nuovi campi di zona possono essere impostati manualmente o utilizzando la procedura guidata **Impostazione ubicazione**. Possono essere utilizzati in qualsiasi query o filtro che utilizza la tabella Ubicazioni.

Non è richiesta alcuna configurazione aggiuntiva per utilizzare i campi della zona.

## <a name="turn-on-the-additional-location-zone-feature"></a>Attivare la funzionalità della zona di ubicazione aggiuntiva

Prima di poter utilizzare la funzionalità *Zona ubicazione aggiuntiva*, tale funzionalità deve essere attivata nel sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e se necessario abilitarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo:** *Gestione Magazzino*
- **Nome funzionalità:** *Zona di ubicazione aggiuntiva*

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