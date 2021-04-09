---
title: Riallocazione del riconoscimento ricavi - Scenario 3
description: Questo argomento descrive uno scenario di riallocazione in cui una nuova riga viene aggiunta a un ordine cliente esistente e fatturato. Quando un nuovo articolo viene aggiunto a un contratto, può essere aggiunto a un nuovo ordine cliente o all'ordine cliente esistente.
author: kweekley
ms.date: 12/21/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 2105973470877f59fd9c4e8d1b1bfc1875a394b3
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833139"
---
# <a name="revenue-recognition-reallocation--scenario-3"></a>Riallocazione del riconoscimento ricavi - Scenario 3

[!include [banner](../includes/banner.md)]

Questo argomento descrive uno scenario di riallocazione in cui una nuova riga viene aggiunta a un ordine cliente esistente e fatturato. Quando un nuovo articolo viene aggiunto a un contratto, può essere aggiunto a un nuovo ordine cliente o all'ordine cliente esistente. Questo scenario mostra anche cosa si verifica quando la contabilità clienti viene aggiornata a causa della riallocazione.

Per questo scenario, l'opzione **Correzioni delle fatture registrate in contabilità clienti** è impostata su **Sì** nella scheda **Riconoscimento ricavi** della pagina **Parametri di contabilità generale** (**Riconoscimento ricavi \> Impostazione \> Parametri di contabilità generale**).

[![Opzione Correzioni delle fatture registrate in contabilità clienti impostata su Sì](./media/25_rev-rec-scenarios.png)](./media/25_rev-rec-scenarios.png)

Viene creato un ordine cliente per il cliente US\_SI\_0003. Il cliente acquista un laptop (numero articolo S0012) e un piano di supporto (numero articolo S0008, "Sustained Engineering Service"). I ricavi per il laptop vengono immediatamente riconosciuti. I ricavi per il piano di supporto saranno differiti e riconosciuti su 12 mesi, come definito dall'intervallo di date nel contratto.

[![Righe ordine cliente per il laptop e il piano di supporto](./media/26_rev-rec-scenarios.png)](./media/26_rev-rec-scenarios.png)

L'ordine cliente è confermato. Poiché entrambi gli articoli sono impostati per l'allocazione dei prezzi dei ricavi, il prezzo dei ricavi viene calcolato quando l'ordine cliente viene confermato. È possibile visualizzare i ricavi che verranno riconosciuti nella pagina **Allocazione del prezzo dei ricavi** (andare alla pagina **Ordine cliente**, riquadro Azioni, scheda **Gestisci**, gruppo **Riconoscimento dei ricavi** e selezionare **Allocazione del prezzo dei ricavi**). I ricavi per il laptop verranno registrati nel conto ricavi per un importo di $1.008,01. I ricavi per il piano di supporto verranno registrati nel conto ricavi differiti per un importo di $190,99. La somma dei prezzi dei ricavi deve essere uguale alla somma delle righe impostate per acquisire l'allocazione dei prezzi dei ricavi ($1.199,00).

[![Pagina Allocazione del prezzo dei ricavi](./media/27_rev-rec-scenarios.png)](./media/27_rev-rec-scenarios.png)

L'ordine cliente è completamente fatturato. La figura seguente mostra la voce contabile registrata per la fattura.

[![Voce contabile per l'ordine cliente completamente fatturato](./media/28_rev-rec-scenarios.png)](./media/28_rev-rec-scenarios.png)

Viene creata anche la programmazione del riconoscimento ricavi. Dopo un po' di tempo, due mesi hanno riconosciuto i ricavi per il piano di supporto.

[![Pagina Programmazione di riconoscimento ricavi dopo due mesi](./media/29_rev-rec-scenarios.png)](./media/29_rev-rec-scenarios.png)

A questo punto, il cliente decide di aggiungere i servizi di installazione (codice articolo S0001). Questo articolo viene aggiunto all'ordine cliente esistente. Al cliente viene richiesto di confermare che desidera modificare l'ordine cliente completamente fatturato e seleziona **Sì**.

[![Ordine cliente dopo l'aggiunta della riga per i servizi di installazione](./media/30_rev-rec-scenarios.png)](./media/30_rev-rec-scenarios.png)

Se questo nuovo articolo è l'unica modifica al contratto del cliente, il processo di riallocazione può essere eseguito ora. Nell'ordine cliente selezionare **Riallocazione del prezzo con nuove righe ordine** per aprire la pagina **Riallocazione del prezzo con nuove righe ordine**. Selezionare tutte le righe per questo ordine cliente, quindi scegliere **Aggiorna riallocazione**. La colonna **Importo riallocato** mostra il nuovo prezzo dei ricavi per ogni riga dell'ordine cliente.

[![Nuovi prezzi dei ricavi nella pagina Riallocazione del prezzo con nuove righe ordine](./media/31_rev-rec-scenarios.png)](./media/31_rev-rec-scenarios.png)

Quindi selezionare **Giustificativo previsto** per visualizzare le voci contabili. Perché l'opzione **Correzioni delle fatture registrate in contabilità clienti** è impostata su **Sì** nella pagina **Parametri di contabilità generale** queste voci contabili verranno registrate nella contabilità generale tramite il documento di credito e verrà creata una nuova fattura nella contabilità clienti.

[![Voci contabili nella pagina Giustificativo previsto](./media/32_rev-rec-scenarios.png)](./media/32_rev-rec-scenarios.png)

Nella pagina **Giustificativo previsto**, le ultime quattro righe annullano la voce contabile originale dalla fattura registrata. Le prime cinque righe sono le nuove voci contabili registrate per la fattura. È importante comprendere che una nuova fattura non viene presentata al cliente. Dopo la riallocazione, il cliente deve ancora $1.276,94, che è l'importo che deve essere registrato nella Contabilità clienti nella nuova voce contabile. L'imposta in contropartita e i ricavi o i ricavi differiti sono pari a $995,83 + $188,69 + $77,94 = $1.262,46. L'importo dei ricavi o dei ricavi differiti è cambiato a causa della riallocazione. La differenza di -$14,48 viene registrata in un conto di compensazione parziale dei ricavi fattura. Questo saldo verrà compensato quando la fattura viene registrata per il nuovo articolo aggiunto all'ordine cliente.

Per completare la riallocazione, selezionare **Processo**. Viene immessa una data di registrazione. Una volta completata la riallocazione, la pagina **Allocazione del prezzo dei ricavi** mostra la riallocazione dei prezzi per tutti e tre gli articoli.

[![Riallocazione dei prezzi per tutti e tre gli articoli nella pagina Allocazione del prezzo dei ricavi](./media/33_rev-rec-scenarios.png)](./media/33_rev-rec-scenarios.png)

È stata aggiornata anche la programmazione del riconoscimento dei ricavi, in base al nuovo prezzo di riallocazione dei ricavi. Dall'ordine cliente, aprire la pagina **Programmazione del riconoscimento dei ricavi**. In precedenza, c'erano 13 righe per l'articolo S0008 (a questo articolo era assegnata una programmazione di 12 mesi). Ora ci sono 39 righe: le 13 righe di programmazione originali, 13 righe di programmazione di storno e 13 righe basate sul nuovo prezzo dei ricavi.

[![Pagina Programmazione di riconoscimento ricavi aggiornata con 39 righe per l'articolo S0008](./media/34_rev-rec-scenarios.png)](./media/34_rev-rec-scenarios.png)

Quando si seleziona **Giustificativo**, il giornale di registrazione fatture mostra la voce contabile originale. Per visualizzare lo storno e la nuova voce contabile dall'ordine cliente, selezionare **Rettifiche ricavi** nel riquadro Azioni, quindi selezionare **Giustificativo**.

Quindi, aprire la pagina **Tutti i clienti** (**Contabilità clienti \> Clienti \> Tutti i clienti**), selezionare il cliente **US\_SI\_0003** e quindi selezionare **Transazioni**. La pagina **Transazioni cliente** mostra la fattura originale (000006), il documento di storno (000006-1) e la nuova fattura (000006-2). La fattura originale e il documento di storno vengono liquidati l'uno con l'altro e hanno un saldo pari a 0 (zero). Visualizzare il giustificativo per ogni documento per vedere l'impatto nella contabilità generale.

[![Fattura originale, documento di storno e nuova fattura nella pagina Transazioni cliente](./media/35_rev-rec-scenarios.png)](./media/35_rev-rec-scenarios.png)

L'ordine cliente viene nuovamente fatturato per l'articolo aggiunto. La fattura totale presentata al cliente è per $300,00 + $19,50 imposta = $319,50. La figura seguente mostra la voce contabile registrata.

[![Pagina Transazioni giustificativo con la voce contabile registrata](./media/36_rev-rec-scenarios.png)](./media/36_rev-rec-scenarios.png)

Poiché la somma dei ricavi e delle vendite è superiore a $319,50, la differenza viene registrata per $14,48. Questo importo compensa il saldo dal conto di compensazione parziale dei ricavi fattura. Tale saldo è stato aggiornato nella nuova voce contabile registrata dopo la riallocazione.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]