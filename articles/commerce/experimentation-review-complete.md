---
title: Promuovere una variante e completare un esperimento
description: Questo argomento descrive come promuovere una variante appropriata e completare un esperimento in Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: c7da601323663d4c1ea76f7cad7bdab8e7632d1c
ms.sourcegitcommit: 7592c2dec0428d56843ab395d2a52c89f77f99b5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2020
ms.locfileid: "4097095"
---
# <a name="promote-a-variation-and-complete-an-experiment"></a>Promuovere una variante e completare un esperimento

Questo argomento descrive come promuovere la variante che ha prodotto i migliori risultati nell'esperimento e come completare l'esperimento. Il diagramma seguente mostra tutti i passaggi relativi alla configurazione e all'esecuzione di un esperimento su un sito Web di e-commerce in Dynamics 365 Commerce. I passaggi aggiuntivi sono esposti in argomenti separati.

[![Percorso utente per sperimentazione - Analisi e completamento](./media/experimentation_review_complete.svg)](./media/experimentation_review_complete.svg#lightbox)

Dopo aver [eseguito l'esperimento](experimentation-run-monitor.md) e raccolto dati sufficienti per determinare quale variante desideri utilizzare sul tuo sito live, promuoverai la variante e terminerai l'esperimento.

## <a name="promote-a-variation"></a>Promuovere una variante
Utilizza i dati e le analisi relative all'esperimento nel servizio di terze parti per decidere quale variante ha prodotto i risultati migliori. È possibile promuoverla sostituendo il contenuto corrente sul sito live con la variante migliore di modo che sia disponibile a tutti gli utenti del sito web.

Per promuovere la variante migliore, seguire questi passaggi. 

1. In Creazione di siti Web di Commerce selezionare **Esperimenti** nel riquadro di spostamento a sinistra e selezionare l'esperimento.
1. Selezionare **Completa esperimento** nella barra dei comandi.
1. Nella casella di dialogo **Completa l'esperimento** , selezionare **Esamina dati dell'esperimento**. Si apre il servizio di terze parti in cui è possibile convalidare le metriche e determinare quale variante ha avuto il rendimento migliore.
1. Nella casella di dialogo **Completa l'esperimento** selezionare la variante migliore e quindi selezionare **Avanti**.
1. Apri il servizio di terze parti e interrompi l'esperimento.
1. In Creazione di siti Web, seleziona **Completa** per sovrascrivere la pagina live originale e pubblicare la variante migliore di modo che sia disponibile a tutti gli utenti del sito web. 

> [!NOTE]
> Se scegli di mantenere la pagina live corrente e di non pubblicare una variante, seleziona **Ripubblica la pagina originale**.

## <a name="delete-your-experiment"></a>Eliminare l'esperimento
Sebbene non sia necessario eliminare un esperimento completato in Commerce, puoi scegliere di eliminarlo per risparmiare spazio o pulire l'area di lavoro. 

Per eliminare un esperimento in Creazione di siti Web di Commerce seguire questi passaggi.

1. Selezionare **Esperimenti** nel riquadro di spostamento a sinistra e selezionare l'esperimento. 
    > [!NOTE]
    > Se l'esperimento è ancora attivo, arrestalo l'esperimento nel servizio di terze parti prima di procedere.
1. Selezionare **Annulla pubblicazione** nella barra dei comandi per rimuovere il contenuto della variante dal sito live.
1. Selezionare **Elimina** per eliminare l'esperimento.

## <a name="previous-step"></a>Passaggio precedente
[Eseguire e monitorare un esperimento](experimentation-run-monitor.md)
