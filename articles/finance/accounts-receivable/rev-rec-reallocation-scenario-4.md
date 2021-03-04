---
title: Riallocazione del riconoscimento ricavi - Scenario 4
description: Questo argomento descrive uno scenario di riallocazione in cui una riga viene rimossa da un ordine cliente esistente e parzialmente fatturato. Questo scenario produce lo stesso risultato, indipendentemente dal fatto che la riga venga rimossa dall'ordine cliente o impostata sullo stato annullato.
author: kweekley
manager: aolson
ms.date: 12/21/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 500c7817795448d7d9759c4ad7a1842df0a9bdc5
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5003282"
---
# <a name="revenue-recognition-reallocation--scenario-4"></a>Riallocazione del riconoscimento ricavi - Scenario 4

[!include [banner](../includes/banner.md)]

Questo argomento descrive uno scenario di riallocazione in cui una riga viene rimossa da un ordine cliente esistente e parzialmente fatturato. Questo scenario produce lo stesso risultato, indipendentemente dal fatto che la riga venga rimossa dall'ordine cliente o impostata sullo stato annullato.

Per questo scenario, l'opzione **Correzioni delle fatture registrate in contabilità clienti** è impostata su **No** nella scheda **Riconoscimento ricavi** della pagina **Parametri di contabilità generale** (**Riconoscimento ricavi \> Impostazione \> Parametri di contabilità generale**).

[![Opzione Correzioni delle fatture registrate in contabilità clienti impostata su No](./media/37_rev-rec-scenarios.png)](./media/37_rev-rec-scenarios.png)

Viene creato un ordine cliente per il cliente US\_SI\_0003. Il cliente sta acquistando un laptop (numero articolo S0012), i servizi di installazione (numero articolo S0001) e un piano di supporto per il laptop (numero articolo S0008, "Sustained Engineering Service"). I ricavi per il laptop e i servizi di installazione vengono immediatamente riconosciuti. I ricavi per il piano di supporto saranno differiti e riconosciuti su 12 mesi, come definito dall'intervallo di date nel contratto.

[![Righe ordine cliente per il laptop, i servizi di installazione e il piano di supporto](./media/38_rev-rec-scenarios.png)](./media/38_rev-rec-scenarios.png)

L'ordine cliente è confermato. Poiché tutti e tre gli articoli sono impostati per l'allocazione dei prezzi dei ricavi, il prezzo dei ricavi viene calcolato quando l'ordine cliente viene confermato. È possibile visualizzare i ricavi che verranno riconosciuti nella pagina **Allocazione del prezzo dei ricavi** (andare alla pagina **Ordine cliente**, riquadro Azioni, scheda **Gestisci**, gruppo **Riconoscimento dei ricavi** e selezionare **Allocazione del prezzo dei ricavi**). I ricavi per il laptop verranno registrati nel conto ricavi per un importo di $995,84. Anche i ricavi per i servizi di installazione verranno registrati nel conto ricavi per un importo di $314,47. I ricavi per il piano di supporto verranno registrati nel conto ricavi differiti per un importo di $188,69. La somma dei prezzi dei ricavi deve essere uguale alla somma delle righe impostate per acquisire l'allocazione dei prezzi dei ricavi ($1.499,00).

[![Pagina Allocazione del prezzo dei ricavi](./media/39_rev-rec-scenarios.png)](./media/39_rev-rec-scenarios.png)

Al cliente viene fatturato il laptop e il piano di supporto, ma non i servizi di installazione. La figura seguente mostra la voce contabile registrata per la fattura.

[![Voce contabile per l'ordine cliente fatturato](./media/40_rev-rec-scenarios.png)](./media/40_rev-rec-scenarios.png)

La voce contabile registra $1.276,94 nella contabilità clienti. Tuttavia, poiché questa fattura è una fattura parziale, i ricavi o i ricavi differiti più l'imposta non corrispondono all'importo della contabilità clienti. La differenza di -$14,47 viene registrata in un conto di compensazione parziale dei ricavi fattura.

Viene creata anche la programmazione del riconoscimento ricavi.

[![Pagina Programmazione del riconoscimento dei ricavi per la fattura parziale](./media/41_rev-rec-scenarios.png)](./media/41_rev-rec-scenarios.png)

Successivamente, il cliente decide di non acquistare i servizi di installazione. Pertanto, quella riga viene rimossa dall'ordine cliente. Tenere presente che l'ordine cliente non può essere confermato di nuovo perché nell'ordine cliente rimangono solo le righe fatturate.

[![Ordine cliente dopo la rimozione della riga per i servizi di installazione](./media/42_rev-rec-scenarios.png)](./media/42_rev-rec-scenarios.png)

Anche se l'ordine cliente non può essere confermato, può essere riallocato. Nell'ordine cliente selezionare **Riallocazione del prezzo con nuove righe ordine** per aprire la pagina **Riallocazione del prezzo con nuove righe ordine**. Selezionare le due righe rimanenti di questo ordine cliente, quindi scegliere **Aggiorna riallocazione**. La colonna **Importo riallocato** mostra il nuovo prezzo dei ricavi per ogni riga rimanente dell'ordine cliente.

[![Nuovi prezzi dei ricavi nella pagina Riallocazione del prezzo con nuove righe ordine](./media/43_rev-rec-scenarios.png)](./media/43_rev-rec-scenarios.png)

Quindi selezionare **Giustificativo previsto** per visualizzare le voci contabili.

[![Voci contabili nella pagina Giustificativo previsto](./media/44_rev-rec-scenarios.png)](./media/44_rev-rec-scenarios.png)

Nella pagina **Giustificativo previsto**, le ultime cinque righe annullano la voce contabile originale dalla fattura registrata. Le prime quattro righe sono le nuove voci contabili registrate per la fattura. È importante comprendere che una nuova fattura non viene presentata al cliente. Dopo la riallocazione, il cliente deve ancora $1.276,94, che è l'importo che deve essere registrato nella Contabilità clienti nella nuova voce contabile. I nuovi ricavi o ricavi differiti più imposte sono pari a $1.276,94. Pertanto, non è necessario eseguire la registrazione nel conto di compensazione dei ricavi della fattura parziale.

Per completare la riallocazione, selezionare **Processo**. Viene immessa una data di registrazione. Una volta completata la riallocazione, la pagina **Allocazione del prezzo dei ricavi** mostra la riallocazione dei prezzi per i due articoli rimanenti.

[![Riallocazione dei prezzi per gli articoli rimanenti nella pagina Allocazione del prezzo dei ricavi](./media/45_rev-rec-scenarios.png)](./media/45_rev-rec-scenarios.png)

È stata aggiornata anche la programmazione del riconoscimento dei ricavi, in base al nuovo prezzo di riallocazione dei ricavi. Dall'ordine cliente, aprire la pagina **Programmazione del riconoscimento dei ricavi**. In precedenza, c'erano 13 righe per l'articolo S0008 (a questo articolo era assegnata una programmazione di 12 mesi). Ora ci sono 39 righe: le 13 righe di programmazione originali, 13 righe di programmazione di storno e 13 righe basate sul nuovo prezzo dei ricavi.

[![Pagina Programmazione di riconoscimento ricavi aggiornata con 39 righe per l'articolo S0008](./media/46_rev-rec-scenarios.png)](./media/46_rev-rec-scenarios.png)

Quando si seleziona **Giustificativo**, il giornale di registrazione fatture mostra la voce contabile originale. Per visualizzare lo storno e la nuova voce contabile dall'ordine cliente, selezionare **Rettifiche ricavi** nel riquadro Azioni, quindi selezionare **Giustificativo**.

Quindi, aprire la pagina **Tutti i clienti** (**Contabilità clienti \> Clienti \> Tutti i clienti**), selezionare il cliente **US\_SI\_0003** e quindi selezionare **Transazioni**. La pagina **Transazioni cliente** mostra solo la fattura originale (000008), insieme alla voce contabile originale. Perché l'opzione **Correzioni delle fatture registrate in contabilità clienti** è impostata su **No** nella pagina **Parametri di contabilità generale** viene aggiornata solo la contabilità generale. Pertanto, le voci contabili stornate e aggiornate non vengono visualizzate. Notare che le transazioni di rettifica ricavi create nello [scenario 3](rev-rec-reallocation-scenario-3.md) sono visualizzate.

[![Voce contabile originale nella pagina Transazioni cliente](./media/47_rev-rec-scenarios.png)](./media/47_rev-rec-scenarios.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]