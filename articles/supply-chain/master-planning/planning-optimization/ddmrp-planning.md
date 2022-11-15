---
title: Pianificazione basata sulla domanda
description: In questo articolo viene descritto come generare ordini pianificati per gli articoli che sono stati impostati come punti di disaccoppiamento.
author: t-benebo
ms.date: 06/30/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-06-30
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 8ba9a6d24923b66259bc8b6cc688ec667cb000de
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740304"
---
# <a name="demand-driven-planning"></a>Pianificazione basata sulla domanda

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

In questo articolo viene descritto come generare ordini pianificati per gli articoli che sono stati impostati come punti di disaccoppiamento.

## <a name="net-flow-and-qualified-demand"></a>Flusso netto e domanda qualificata

Durante la pianificazione generale, il sistema applica il concetto di *flusso netto* per stabilire la quantità disponibile effettiva in base alle scorte disponibili effettive, più le scorte ordinate (ordini di fornitura esistenti non ancora ricevuti), meno ciò che viene chiamata *domanda qualificata* (vendite qualificate imminenti), come mostrato nella figura di seguito. Quando il sistema determina a quale zona di buffer appartiene un articolo e quale deve essere la quantità ordinata, valuta il flusso netto e non le scorte disponibili effettive.

![Esempio di un grafico del calcolo del flusso netto.](media/ddmrp-net-flow-example.png "Esempio di un grafico del calcolo del flusso netto")

Quando un ordine pianificato viene attivato durante l'esecuzione di una pianificazione, la quantità ordinata sarà pari al livello massimo meno il flusso netto. Per assegnare una priorità all'ordine, il sistema usa la funzionalità di [pianificazione basata sulla priorità](priority-based-planning.md) anziché le date del fabbisogno. La pianificazione del fabbisogno di materiale basato sulla domanda (DDMRP) assegna la priorità di un ordine pianificato in base alla quantità ordinata come percentuale delle scorte massime. Nell'immagine precedente, la quantità ordinata rappresenta il 53% della quantità massima. Pertanto, la priorità dell'ordine per il rifornimento sarà 53. (Per avere del contesto, 0 è la priorità più alta e 100 è la priorità più bassa.)

La *domanda qualificata* è pari alla domanda arretrata più la domanda odierna più i picchi degli ordini qualificati futuri. La figura seguente mostra un esempio dei livelli di domanda per oggi (12 giugno) e per i successivi tre giorni. DDMRP permette di impostare una soglia di picco degli ordini per identificare la domanda in eccesso rispetto alle normali aspettative. Se la soglia è di 25 pezzi, due delle date future mostrate nella figura saranno qualificate come picchi degli ordini. Si deve assegnare una soglia di picco degli ordini per ogni singolo prodotto mediante la relativa pagina **Copertura articolo**, come descritto in [Impostare i buffer per un articolo punto di disaccoppiamento](ddmrp-buffer-profile-and-levels.md#set-up-buffers).

![Esempio di un grafico del calcolo della domanda qualificata.](media/ddmrp-net-qualified-demand-example.png "Esempio di un grafico del calcolo della domanda qualificata")

Considerato che non esiste domanda arretrata, ora è possibile aggiungere la domanda odierna (18) alle quantità dei due picchi degli ordini (26 e 29) per ottenere una domanda qualificata pari a 73. Anche se c'è domanda per il 23 giugno, questa non viene inclusa nel calcolo del flusso netto perché DDMRP attiva l'ordine pianificato in modo diverso rispetto ai gruppi di copertura della pianificazione tradizionale.

## <a name="generating-planned-orders-with-ddmrp"></a>Generazione di ordini pianificati con DDMRP

Durante l'esecuzione di una pianificazione, viene automaticamente creato un nuovo ordine pianificato se il flusso netto per un articolo scende al di sotto del punto di riordino. Quando si usa DDMRP, in genere la pianificazione viene eseguita con cadenza giornaliera. È quindi necessario verificare i livelli delle scorte ogni giorno per determinare quali articoli devono essere riforniti.

L'immagine seguente mostra un esempio di situazione in cui si ha un ordine di 18 pezzi il 20 giugno, 29 pezzi il 21 giugno, 26 pezzi il 22 giugno e 20 pezzi il 23 giugno. Poiché la soglia di picco è impostata a 25 pezzi, due di questi ordini vengono contrassegnati come picchi. Ci sono 220 pezzi di questo articolo disponibili.

![Esempio di pianificazione 1.](media/ddmrp-planning-example-1.png "Esempio di pianificazione 1")

Se si esegue la pianificazione generale ora, verrà generato un ordine pianificato se il flusso netto scende al di sotto del punto di riordino (219 pezzi in questo esempio).

![Esempio di pianificazione 2.](media/ddmrp-planning-example-2.png "Esempio di pianificazione 2")

Questo esempio produce un ordine di acquisto pianificato per una quantità di 130, ovvero il livello massimo meno il flusso netto. All'ordine pianificato viene assegnata una priorità di 53,07, in base alla relativa percentuale della quantità massima. Poiché questi valori sono stati riscontrati il 20 giugno, il sistema crea un ordine pianificato con data 20 giugno più il lead time disaccoppiato per l'articolo (cinque giorni lavorativi in questo esempio). Poiché cinque giorni lavorativi corrispondono a una settimana dalla data odierna, l'ordine pianificato avrà data 27 giugno.

> [!NOTE]
> La pianificazione generale calcola soltanto gli articoli disaccoppiati mediante DDMRP. Tutti gli altri articoli vengono calcolati mediante la pianificazione dei fabbisogni di materiali standard (MRP).
