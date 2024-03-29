---
title: Ricerca di azioni
description: In questo articolo viene descritta la funzionalità di ricerca di azioni. La ricerca di azioni consente di individuare ed eseguire azioni in una pagina.
author: jasongre
ms.date: 03/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 62303
ms.assetid: 62c70de0-fdde-4417-8e08-0583fb095a40
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6277c37ac43b8cc05c8b53da5ca0a1909f58c4f9
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8070036"
---
# <a name="action-search"></a>Ricerca di azioni

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

In questo articolo viene descritta la funzionalità di ricerca di azioni. La ricerca di azioni consente di individuare ed eseguire azioni in una pagina.

## <a name="introduction"></a>Introduzione

Le pagine espongono principalmente i controlli presenti nei riquadri azioni, sia il riquadro azioni standard visualizzato nella parte superiore di una pagina sia le barre degli strumenti visualizzate in diverse aree della pagina. Nelle versioni precedenti, una funzionalità descrizione dei tasti consente di accedere rapidamente a qualsiasi pulsante in un riquadro azioni premendo il tasto ALT e una serie di lettere.

[![keyTipsAX6.](./media/keytipsax6.png)](./media/keytipsax6.png)

La funzionalità di ricerca delle azioni sostituisce le descrizioni dei tasti che non sono più disponibili. La nuova funzionalità consente di trovare rapidamente ed eseguire un pulsante da qualsiasi riquadro azioni visibile.

## <a name="using-action-search"></a>Utilizzo della ricerca azioni

Per utilizzare la funzionalità di ricerca azioni, effettuare le operazioni indicate di seguito.

1. Nel riquadro azioni fare clic nel campo di **ricerca azioni**. (Il campo di **ricerca azioni** contiene un'icona a forma di lente d'ingrandimento).
2. Digitare integralmente o parzialmente il nome del pulsante che si desidera eseguire. È inoltre possibile eseguire la ricerca utilizzando le parole dal "percorso" del pulsante. (Per ulteriori informazioni, vedere la sezione successiva dell'articolo). In genere, un pulsante verrà visualizzato vicino alla parte superiore dell'elenco dei risultati dopo aver digitato da due a quattro caratteri.
3. Individuare ed eseguire il pulsante nell'elenco risultati (mediante il mouse o tastiera).

Dopo che il pulsante viene eseguito, lo stato attivo torna all'ultima posizione nella pagina, in modo che sia possibile continuare a lavorare.

[![campo-di-ricerca-azioni.](./media/action-search-field.png)](./media/action-search-field.png)

È inoltre possibile avviare la ricerca azioni premendo i tasti CTRL+/ o ALT+Q. Premere di nuovo i tasti di scelta rapida per riportare lo stato attivo all'ultima posizione nella pagina.

## <a name="understanding-the-results-list"></a>Interpretazione dell'elenco dei risultati

Spesso, è necessario conoscere l'ubicazione e il contesto di un pulsante per comprendere completamente lo scopo di tale pulsante. Di conseguenza, nell'elenco dei risultati vengono mostrate informazioni aggiuntive per ciascun articolo, al fine di aiutare a comprendere esattamente quali pulsanti vengono visualizzati nell'elenco. In particolare, verrà visualizzato "il percorso" del pulsante. Questo percorso può includere le etichette dei seguenti elementi di interfaccia utente, a seconda dei casi:

- Scheda del riquadro azioni
- Gruppo pulsanti
- Pulsante di menu (se il pulsante è all'interno di un pulsante di menu)
- Separatore di menu (se il pulsante è interno un gruppo denominato all'interno di un pulsante di menu)
- Gruppo o scheda nella pagina (ad esempio, il nome di una scheda dettaglio)

Ad esempio, l'utente digita **tot** nel campo di **ricerca azioni** ed esamina l'elenco risultati. La prima voce, per un pulsante denominato **Totali**, viene evidenziata. Viene inoltre visualizzato un percorso di pulsante di **Ordine cliente** &gt; **Visualizza**. La parte **Ordine cliente** del percorso corrisponde alla scheda **Ordine cliente** nel riquadro azioni e la parte **Visualizza** del percorso corrisponde al gruppo **Visualizza** in quella scheda. Analogamente, il percorso del pulsante **Sconto totale** (**Vendi** &gt; **Calcola**) indica che questo pulsante si trova nel gruppo **Calcola** nella scheda **Vendi** del riquadro azioni. Di conseguenza, queste informazioni aiutano a comprendere esattamente quale pulsante verrà attivato dalla ricerca di azioni (se si seleziona tale pulsante nell'elenco dei risultati).

[![campo-di-ricerca-azioni-con-dati.](./media/action-search-field-with-data.png)](./media/action-search-field-with-data.png)

Nell'esempio precedente, la ricerca azioni ha mostrato i risultati dal riquadro azioni standard nella parte superiore della pagina. Tuttavia, la ricerca azioni mostra anche i risultati delle barre degli strumenti visibili situate in altri punti della pagina. Ad esempio, se si cerca il pulsante **Scorte disponibili** situato nella scheda dettaglio **Righe ordine cliente**. In questo caso, il percorso del pulsante nell'elenco dei risultati (**Righe ordine cliente** &gt; **Scorte** &gt; **Visualizza**) indica che questo pulsante è situato sotto l'intestazione **Visualizza** nel pulsante di menu **Scorte** nella scheda dettaglio **Righe ordine cliente**.

[![scorte-disponibili.](./media/on-hand-inventory.png)](./media/on-hand-inventory.png)

> [!NOTE]
> Esistono alcuni pulsanti che non vengono visualizzati nella ricerca di azioni. Sono inclusi i pulsanti di dialogo a discesa e i pulsanti di moduli secondari. 

## <a name="action-search-vs-navigation-search"></a>Confronto tra ricerca di azioni e ricerca di navigazione

La ricerca di azioni è destinata alla ricerca e all'esecuzione di azioni in una pagina, ma è disponibile un meccanismo di ricerca distinto che consente di cercare e passare alle pagine. Per ulteriori informazioni su tale funzionalità, vedere l'articolo [Ricerca per navigazione](navigation-search.md).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]