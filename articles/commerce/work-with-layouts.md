---
title: Utilizzare i layout preimpostati
description: In questo argomento viene descritto come utilizzare i layout preimpostati in Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f31dfa1fdbb3732610748abe4a9de851033f2b89
ms.sourcegitcommit: 7a1d01122790b904e2d96a7ea9f1d003392358a6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/17/2020
ms.locfileid: "3269891"
---
# <a name="work-with-preset-layouts"></a>Utilizzare i layout preimpostati


[!include [banner](includes/banner.md)]

In questo argomento viene descritto come utilizzare i layout preimpostati in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Prima di completare le procedure in questo argomento, assicurarsi di leggere [Layout personalizzati e preimpostati](templates-layouts-overview.md#preset-and-custom-layouts). Per una panoramica generale, vedere [Panoramica modelli e layout](templates-layouts-overview.md).

## <a name="create-a-new-preset-layout"></a>Creare un nuovo layout preimpostato

Un layout preimpostato può essere creato in due modi. È possibile salvare un layout personalizzato esistente come nuovo layout preimpostato oppure creare un layout preimpostato da zero.

### <a name="create-a-preset-layout-from-an-existing-custom-layout"></a>Creare un layout preimpostato da un layout personalizzato esistente

Per creare un layout preimpostato da un layout personalizzato esistente, procedere come segue.

1. Aprire una pagina esistente che attualmente non utilizza un layout preimpostato e che ha una struttura di modulo che si intende riutilizzare per altre pagine del sito.
1. Selezionare **Modifica** per estrarre la pagina.
1. Selezionare **Salva come nuovo layout**. Viene visualizzata la finestra di dialogo **Salva come nuovo layout** .
1. Immettere un nome e una descrizione per il layout preimpostato. I valori immessi sono visibili ad altri autori quando questi creano nuove pagine a partire dal layout o passano a tale layout. Di conseguenza, immettere valori che saranno utili ad altri autori di pagine.
1. Selezionare **OK**.

Il layout preimpostato sarà ora disponibile quando si creano nuove pagine o si seleziona un layout diverso per una pagina nella stessa gerarchia di modelli.

> [!TIP]
> Per determinare rapidamente se una pagina specifica è attualmente associata a un layout preimpostato, selezionare la pagina nella visualizzazione con l'elenco di pagine ed esaminare i metadati del layout nel riquadro delle proprietà a destra.

### <a name="create-a-new-preset-layout"></a>Creare un nuovo layout preimpostato

Per creare un layout preimpostato da zero, procedere come segue.

1. Nel pannello di navigazione a sinistra, selezionare **Layout**.
1. Selezionare **Nuovo layout**. Viene visualizzata la finestra di dialogo **Nuovo layout**.
1. Selezionare il modello da utilizzare per il layout preimpostato.
1. Immettere un nome e una descrizione per il layout preimpostato. I valori immessi sono visibili ad altri autori quando questi creano nuove pagine a partire dal layout o passano a tale layout. Di conseguenza, immettere valori che saranno utili ad altri autori di pagine.
1. Selezionare **OK** per creare il nuovo layout preimpostato e aprire l'editor di layout.
1. Nell'editor di layout, aggiungere e configurare moduli utilizzando l'albero a sinistra e il riquadro delle proprietà a destra. (il processo è analogo a quello per l'aggiunta e la configurazione di moduli per un modello nell'editor di modelli). La disposizione dei moduli e le impostazioni predefinite bloccate diventano la configurazione di moduli centralizzata di qualsiasi pagina che utilizza questo layout preimpostato.

## <a name="modify-a-preset-layout"></a>Modificare un layout preimpostato

Per modificare un layout preimpostato, attenersi alla procedura indicata di seguito.

1. Nel pannello di navigazione a sinistra, selezionare **Layout**.
1. Nell'editor di layout, nell'albero a sinistra, selezionare il modulo da modificare. Quindi eseguire uno qualsiasi delle seguenti operazioni:

    - Per spostare un modulo verso l'alto o verso il basso nel relativo modulo padre, selezionare il pulsante con i puntini di sospensione (**...**) per il modulo, quindi selezionare **Sposta su** o **Sposta giù**.
    - Per modificare le impostazioni predefinite di un modulo, utilizzare il riquadro delle proprietà per immettere valori predefiniti ed eventualmente bloccarli per tutte le pagine downstream.
    - Per aggiungere nuovi moduli o frammenti a moduli contenitore, selezionare il pulsante con i puntini di sospensione e quindi **Aggiungi modulo** o **Aggiungi frammento**.
    - Per rimuovere un modulo dal layout, selezionare il pulsante con i puntini di sospensione e quindi **Elimina**.

## <a name="change-a-preset-layout-theme"></a>Modificare il tema di un layout preimpostato

Una procedura tipica consiste nell'impostare un tema predefinito per tutte le pagine che utilizzano un layout preimpostato.

Per impostare o modificare il tema di tutte le pagine figlio che utilizzano il layout preimpostato, effettuare le seguenti operazioni.

1. Nell'editor di layout, nell'albero a sinistra, selezionare il modulo contenitore pagina (in genere, questo modulo è il secondo nodo ed è denominato **Pagina predefinita**).
1. Nel riquadro delle proprietà a destra, nel campo **Tema**, selezionare un tema.

## <a name="save-check-in-preview-and-publish-a-preset-layout"></a>Salva, archiviare, visualizzare in anteprima e pubblicare un layout preimpostato

Per salvare e archiviare il layout preimpostato, effettuare le seguenti operazioni.

1. Selezionare **Salva** nella parte superiore dell'editor di layout. Le modifiche salvate non influiscono sulle pagine downstream fino a che non vengono archiviate.
1. Selezionare **Fine modifica**. Le modifiche sono ora individuabili per i flussi di lavoro downstream.

Per visualizzare l'anteprima delle modifiche, aprire una pagina esistente che utilizza il layout preimpostato o creare una nuova pagina a partire dal layout.

Dopo avere visualizzato un'anteprima delle modifiche al layout preimpostato, eseguire una di queste operazioni per pubblicare il layout sul sito live:

* Andare a **Layout**, selezionare il layout e quindi **Pubblica**.
* Selezionare il nome del layout per aprire l'editor del layout, quindi selezionare **Pubblica**.
* Pubblicare una pagina che fa riferimento al layout non pubblicato. Il layout viene pubblicato automaticamente.

> [!WARNING]
> Molteplici pagine possono fare riferimento ai layout preimpostati. Quando si pubblica un layout preimpostato, tenere presente che è possibile alterare il layout di molteplici pagine.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica modelli e layout](templates-layouts-overview.md)

[Utilizzare i modelli](work-with-templates.md)
