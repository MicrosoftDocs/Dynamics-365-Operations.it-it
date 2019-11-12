---
title: Contratti di garanzia
description: In questo argomento vengono descritti i contratti di garanzia in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 08/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: da60d098aff96780ca1e40832db34e3c9cc835e7
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2019
ms.locfileid: "2569687"
---
# <a name="warranty-agreements"></a>Contratti di garanzia

[!include [banner](../../includes/banner.md)]

 


In Gestione cespiti, è possibile impostare i termini di garanzia che possono essere associati a un cespite o a un tipo di cespite. I termini di garanzia vengono creati per un periodo specifico. La garanzia può essere impostata per fornire una copertura totale o parziale ed è possibile impostare i termini relativi a ore, spese e articoli.

Il primo passo consiste nel creare tutti i contratti di garanzia fornitore relativi all'attrezzatura aziendale. Successivamente, si associano i contratti di garanzia a cespiti o tipi di cespite. I contratti di garanzia fornitore vengono utilizzati solo a scopo informativo. Se la garanzia fornitore viene impostata in un cespite, è possibile visualizzare il periodo di copertura della garanzia nel cespite.

## <a name="create-a-warranty-agreement"></a>Creare un contratto di garanzia

Un contratto di garanzia può includere varie righe del contratto per coprire la garanzia relativa a ore, spese e articoli.

1. Selezionare **Gestione cespiti** \> **Impostazione** \> **Cespiti** \>**Garanzia**.
2. Selezionare **Nuovo** per creare un prodotto.
3. Nel campo **Garanzia**, immettere un ID garanzia.
4. Nel campo **Nome** immettere una descrizione.

    Nella Scheda dettaglio **Dettagli**, il campo **Cespiti** visualizza il numero di cespiti attivi che utilizzano il contratto di garanzia.

5. Nelle Schede dettaglio **Garanzia ore** e **Garanzia articoli**, seguire questi passaggi per aggiungere righe che devono essere incluse in un contratto di garanzia relativo a ore o articoli:

    1. Selezionare **Aggiungi riga** per aggiungere una nuova condizione alla garanzia. Un numero di riga sequenziale viene immesso automaticamente nel campo **Riga**.
    2. Nel campo **Periodo** selezionare il tipo di periodo di garanzia.
    3. Nel campo **Intervallo** immettere un numero. Questo campo definisce il numero di periodi per i quali la garanzia deve essere valida.
    4. Nel campo **Percentuale**, immettere la percentuale di copertura per la riga della garanzia. La percentuale indica quanto è coperto dalla società.

![Pagina della garanzia](media/01-warranty.png)
