---
title: Visualizzazione cespiti
description: In questo argomento viene descritta la visualizzazione cespiti in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectTree, EntAssetFunctionalLocationTree
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bc4cd9ada9c1f64b434cd657eb5f5654c1328ef4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431283"
---
# <a name="asset-view"></a>Visualizzazione cespiti

[!include [banner](../../includes/banner.md)]

 

In questo argomento viene descritta la visualizzazione cespiti in Gestione cespiti. La pagina **Visualizzazione cespiti** mostra i cespiti attivi e le unità funzionali in una visualizzazione struttura. Di conseguenza, è possibile ottenere facilmente una panoramica delle relazioni cespiti alle unità funzionali. Inoltre, è possibile visualizzare informazioni dettagliate sulle unità funzionali, Cespiti e distinte base (DBA) correlate. È inoltre possibile visualizzare una veloce panoramica delle richieste di intervento di manutenzione e degli ordini di lavoro attivi correlati a un cespite.

1. Selezionare **Gestione cespiti** \> **Comune** \> **Cespiti** \> **Visualizzazione cespiti**.
2. Per cambiare la visualizzazione nella pagina, selezionare un nuovo valore nel campo **Visualizzazione**.

    > [!NOTE]
    > La visualizzazione predefinita che viene visualizzata quando si apre la pagina **Visualizzazione cespiti** dipende dal valore selezionato nel campo **Visualizzazione** della scheda **Cespiti** della pagina **Parametri di gestione cespiti** (**Gestione cespiti** \> **Impostazione** \> **Parametri di gestione cespiti**).

Nel lato destro della pagina, schede dettaglio mostrano i dettagli della visualizzazione selezionata.

Il percorso di navigazione visualizzato sopra la visualizzazione struttura mostra la selezione corrente nella visualizzazione struttura. Questo percorso di navigazione utilizza il seguente formato:

ID unità funzionale /ID unità funzionale (se sono disponibili più di una unità funzionale) \>ID cespite/ID cespite (se sono disponibili più di un cespite) - numero di articolo.

Se è stato selezionato un cespite nella visualizzazione struttura, è possibile selezionare **Richieste attive** o **Ordini di lavoro attivi** per visualizzare le richieste di intervento di manutenzione o gli ordini di lavoro correlati al cespite. È inoltre possibile selezionare **Apri** \> **Unità funzionale**, **Cespite**, **DBA cespiti** per aprire la visualizzazione correlata.

L'opzione **Unità funzionali cespiti** selezionabile nel campo **Visualizzazione** è inoltre disponibile in qualsiasi ricerca del cespite in cui è possibile selezionare un cespite. La visualizzazione struttura viene visualizzata in una scheda **Visualizzazione cespiti**, ad esempio, dove [creare un cespite](../objects/create-an-object.md), creare una richiesta di intervento di manutenzione o creare un ordine di lavoro.
