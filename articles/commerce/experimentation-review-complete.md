---
title: Promuovere una variante e completare un esperimento
description: Questo articolo descrive come promuovere una variante appropriata e completare un esperimento in Dynamics 365 Commerce.
author: sushma-rao
ms.date: 06/07/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.openlocfilehash: 3e9a978551622bbb14d9213f607d9dfabe42672a
ms.sourcegitcommit: ddcb62bb5fbf26a1178c2bb1aec45a3d2362339e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/07/2022
ms.locfileid: "8942745"
---
# <a name="promote-a-variation-and-complete-an-experiment"></a>Promuovere una variante e completare un esperimento

Questo articolo descrive come promuovere la variante che ha prodotto i migliori risultati nell'esperimento e come completare l'esperimento. Il diagramma seguente mostra tutti i passaggi relativi alla configurazione e all'esecuzione di un esperimento su un sito Web di e-commerce in Dynamics 365 Commerce. I passaggi aggiuntivi sono esposti in articoli separati.

[![Percorso utente sperimentazione - Analisi e completamento.](./media/experimentation_review_complete.svg)](./media/experimentation_review_complete.svg#lightbox)

Dopo aver [eseguito l'esperimento](experimentation-run-monitor.md) e raccolto dati sufficienti per determinare quale variante desideri utilizzare sul tuo sito live, promuoverai la variante e terminerai l'esperimento.

## <a name="promote-a-variation"></a>Promuovere una variante
Utilizza i dati e le analisi relative all'esperimento nel servizio di terze parti per decidere quale variante ha prodotto i risultati migliori. È possibile promuoverla sostituendo il contenuto corrente sul sito live con la variante migliore di modo che sia disponibile a tutti gli utenti del sito web.

Per promuovere la variante migliore, seguire questi passaggi. 

1. In Creazione di siti Web di Commerce selezionare **Esperimenti** nel riquadro di spostamento a sinistra e selezionare l'esperimento.
1. Selezionare **Completa esperimento** nella barra dei comandi.
1. Nella casella di dialogo **Completa l'esperimento**, selezionare **Esamina dati dell'esperimento**. Si apre il servizio di terze parti in cui è possibile convalidare le metriche e determinare quale variante ha avuto il rendimento migliore.
1. Nella casella di dialogo **Completa l'esperimento** selezionare la variante migliore e quindi selezionare **Avanti**.
1. Apri il servizio di terze parti e interrompi l'esperimento.
1. In Creazione di siti Web, seleziona **Completa** per sovrascrivere la pagina live originale e pubblicare la variante migliore di modo che sia disponibile a tutti gli utenti del sito web. 

> [!NOTE]
> Se scegli di mantenere la pagina live corrente e di non pubblicare una variante, seleziona **Ripubblica la pagina originale**.

## <a name="delete-your-experiment"></a>Eliminare l'esperimento
Sebbene non sia necessario eliminare un esperimento completato in Commerce, puoi scegliere di eliminarlo per risparmiare spazio o pulire l'area di lavoro. 

Per eliminare un esperimento completato in Creazione di siti Web di Commerce segui questi passaggi.

1. Selezionare **Esperimenti** nel riquadro di spostamento a sinistra e selezionare l'esperimento. 
    > [!NOTE]
    > Se l'esperimento è ancora attivo, arrestalo l'esperimento nel servizio di terze parti prima di procedere.
1. Selezionare **Annulla pubblicazione** nella barra dei comandi per rimuovere il contenuto della variante dal sito live.
1. Selezionare **Elimina** per eliminare l'esperimento.

## <a name="previous-step"></a>Passaggio precedente
[Eseguire e monitorare un esperimento](experimentation-run-monitor.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
