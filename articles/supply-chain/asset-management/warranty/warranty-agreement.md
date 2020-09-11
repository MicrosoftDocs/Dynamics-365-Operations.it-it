---
title: Contratti di garanzia
description: In questo argomento vengono descritti i contratti di garanzia in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 08/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f049165fd12dfae672293e0c30ddb186ad3ed12c
ms.sourcegitcommit: 18c5ef10e311f3dd2dbf45c6439ae6beff921af8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2020
ms.locfileid: "3719240"
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

5. Nella scheda dettaglio **Righe garanzia** attenersi alla seguente procedura per aggiungere righe da includere in un contratto di garanzia:

    1. Selezionare **Aggiungi riga** per aggiungere una nuova condizione alla garanzia. Un numero di riga sequenziale viene immesso automaticamente nel campo **Riga**.
    2. Nel campo **Periodo** selezionare il tipo di periodo di garanzia.
    3. Nel campo **Intervallo** immettere un numero. Questo campo definisce il numero di periodi per i quali la garanzia deve essere valida.
    4. Nel campo **Percentuale**, immettere la percentuale di copertura per la riga della garanzia. La percentuale indica quanto è coperto dalla società.

![Pagina della garanzia](media/01-warranty.png)
