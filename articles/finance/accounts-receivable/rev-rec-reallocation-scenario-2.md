---
title: Riallocazione del riconoscimento ricavi - Scenario 2
description: Questo argomento descrive uno scenario di riallocazione in cui vengono immessi due ordini cliente e quindi il cliente aggiunge un articolo al contratto dopo che il primo ordine cliente è stato fatturato. Quando un nuovo articolo viene aggiunto a un contratto, può essere aggiunto a un nuovo ordine cliente o all'ordine cliente esistente.
author: kweekley
ms.date: 12/21/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 4026b8c69e51cb33c64bcf71a62a13b28b86bd49
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2022
ms.locfileid: "8726156"
---
# <a name="revenue-recognition-reallocation--scenario-2"></a>Riallocazione del riconoscimento ricavi - Scenario 2

[!include [banner](../includes/banner.md)]

Questo argomento descrive uno scenario di riallocazione in cui vengono immessi due ordini cliente e quindi il cliente aggiunge un articolo al contratto dopo che il primo ordine cliente è stato fatturato. Quando un nuovo articolo viene aggiunto a un contratto, può essere aggiunto a un nuovo ordine cliente o all'ordine cliente esistente.

Per questo scenario, l'opzione **Correzioni delle fatture registrate in contabilità clienti** è impostata su **No** nella scheda **Riconoscimento ricavi** della pagina **Parametri di contabilità generale** (**Riconoscimento ricavi \> Impostazione \> Parametri di contabilità generale**).

[![Opzione Correzioni delle fatture registrate in contabilità clienti impostata su No.](./media/12_rev-rec-scenarios.png)](./media/12_rev-rec-scenarios.png)

Viene creato un ordine cliente per il cliente US\_SI\_0003. Il cliente sta acquistando servizi di installazione (numero articolo S0001) e un piano di supporto (numero articolo S0008) per un laptop, ma non ha ancora selezionato il laptop. I ricavi per i servizi di installazione verranno differiti fino alla data di acquisto del laptop. I ricavi per il piano di supporto saranno differiti e riconosciuti su 12 mesi, come definito dall'intervallo di date nel contratto.

[![Righe ordine cliente per i servizi di installazione e il piano di supporto.](./media/13_rev-rec-scenarios.png)](./media/13_rev-rec-scenarios.png)

L'ordine cliente è confermato. Poiché entrambi gli articoli sono impostati per l'allocazione dei prezzi dei ricavi, il prezzo dei ricavi viene calcolato quando l'ordine cliente viene confermato. È possibile visualizzare i ricavi che verranno riconosciuti nella pagina **Allocazione del prezzo dei ricavi** (andare alla pagina **Ordine cliente**, riquadro Azioni, scheda **Gestisci**, gruppo **Riconoscimento dei ricavi** e selezionare **Allocazione del prezzo dei ricavi**). I ricavi per i servizi di installazione verranno registrati nel conto ricavi differiti per un importo di $250,00. Anche i ricavi per il piano di supporto verranno registrati nel conto ricavi differiti per un importo di $150,00. La somma dei prezzi dei ricavi deve essere uguale alla somma delle righe impostate per acquisire l'allocazione dei prezzi dei ricavi ($400,00).

[![Pagina Allocazione del prezzo dei ricavi.](./media/14_rev-rec-scenarios.png)](./media/14_rev-rec-scenarios.png)

L'ordine cliente è completamente fatturato. La figura seguente mostra la voce contabile registrata per la fattura.

[![Voce contabile per l'ordine cliente completamente fatturato.](./media/15_rev-rec-scenarios.png)](./media/15_rev-rec-scenarios.png)

Viene creata anche la programmazione per il riconoscimento ricavi, ma i ricavi non sono ancora stati riconosciuti.

[![Pagina Programmazione del riconoscimento ricavi.](./media/16_rev-rec-scenarios.png)](./media/16_rev-rec-scenarios.png)

Pochi giorni dopo, il cliente seleziona un laptop. Viene immesso un secondo ordine cliente per il cliente.

[![Riga ordine cliente per il laptop.](./media/17_rev-rec-scenarios.png)](./media/17_rev-rec-scenarios.png)

Il secondo ordine cliente è confermato. Poiché questo ordine cliente contiene solo una riga, l'allocazione del prezzo dei ricavi non viene eseguita quando l'ordine cliente viene confermato. L'allocazione del prezzo dei ricavi si verifica solo se sono presenti due o più articoli univoci e se tali articoli sono impostati per l'allocazione dei prezzi dei ricavi.

Se questo nuovo ordine cliente è l'unica modifica al contratto del cliente, il processo di riallocazione può ora essere eseguito. In uno dei due ordini cliente selezionare **Riallocazione del prezzo con nuove righe ordine** per aprire la pagina **Riallocazione del prezzo con nuove righe ordine**. In alternativa, andare a **Riconoscimento dei ricavi \> Attività periodiche \> Riallocazione del prezzo con nuove righe ordine**. Selezionare i due ordini cliente e le righe corrispondenti, quindi scegliere **Aggiorna riallocazione**. La colonna **Importo riallocato** mostra il nuovo prezzo dei ricavi per ogni riga dell'ordine cliente.

[![Nuovi prezzi dei ricavi nella pagina Riallocazione del prezzo con nuove righe ordine.](./media/18_rev-rec-scenarios.png)](./media/18_rev-rec-scenarios.png)

Quindi selezionare **Giustificativo previsto** per visualizzare le voci contabili che verranno registrati solo nella contabilità generale. Dal momento che l'opzione **Correzioni delle fatture registrate in contabilità clienti** è impostata su **No** nella pagina **Parametri di contabilità generale**, non verrà modificato nulla nella contabilità clienti al momento dell'elaborazione della riallocazione.

[![Voci contabili nella pagina Giustificativo previsto.](./media/19_rev-rec-scenarios.png)](./media/19_rev-rec-scenarios.png)

Nella pagina **Giustificativo previsto**, le ultime tre righe annullano la voce contabile originale dalla fattura registrata. Le prime quattro righe sono la nuova voce contabile registrata per la fattura. È importante comprendere che una nuova fattura non viene presentata al cliente. Dopo la riallocazione, il cliente deve ancora $426,00, che è l'importo che deve essere registrato nella Contabilità clienti nella nuova voce contabile. L'imposta in contropartita e i ricavi differiti sono pari a $188,69 + $314,48 + $26,00 = $529,17. L'importo dei ricavi differiti è cambiato a causa della riallocazione. La differenza di $103,17 viene registrata in un conto di compensazione parziale dei ricavi fattura. Questo saldo verrà compensato quando la fattura viene registrata per il secondo ordine cliente incluso nella riallocazione.

Per completare la riallocazione, selezionare **Processo**. Viene richiesta una data di registrazione, anche se non viene registrato nulla. Una volta completata la riallocazione, la pagina **Allocazione del prezzo dei ricavi** per ogni ordine cliente mostrerà l'allocazione dei prezzi per tutti gli articoli in entrambi gli ordini cliente. In altre parole, la pagina **Allocazione del prezzo dei ricavi** per ogni ordine cliente includerà un articolo che non esiste in quell'ordine cliente perché fa parte dello stesso contratto ma in un ordine cliente diverso.

> [!TIP]
> Per fornire un contesto sul motivo per cui vengono visualizzati questi elementi aggiuntivi, è possibile aggiungere altre colonne alla griglia, ad esempio **ID riallocazione** e **Ordine cliente**.
> 
> [![Colonne aggiuntive nella pagina Allocazione del prezzo dei ricavi.](./media/20_rev-rec-scenarios.png)](./media/20_rev-rec-scenarios.png)

Nell'ordine cliente 00036, è stata aggiornata anche la programmazione del riconoscimento dei ricavi, in base al nuovo prezzo di riallocazione dei ricavi. Da questo ordine cliente, aprire la pagina **Programmazione del riconoscimento dei ricavi**. In precedenza, c'erano 13 righe per l'articolo S0008 (a questo articolo era assegnata una programmazione di 12 mesi). Ora ci sono 39 righe: le 13 righe di programmazione originali, 13 righe di programmazione di storno e 13 righe basate sul nuovo prezzo dei ricavi.

[![Pagina Programmazione di riconoscimento ricavi aggiornata con 39 righe per l'articolo S0008.](./media/21_rev-rec-scenarios.png)](./media/21_rev-rec-scenarios.png)

Allo stesso modo, in precedenza c'erano due righe per l'articolo S0001, ma ora ce ne sono sei.

[![Pagina Programmazione di riconoscimento ricavi aggiornata con sei righe per l'articolo S0001.](./media/22_rev-rec-scenarios.png)](./media/22_rev-rec-scenarios.png)

Quando si seleziona **Giustificativo** nell'ordine cliente 000036, il giornale di registrazione fatture mostra la voce contabile originale. Per visualizzare lo storno e la nuova voce contabile dall'ordine cliente, selezionare **Rettifiche ricavi** nel riquadro Azioni, quindi selezionare **Giustificativo**.

[![Ordine cliente 000036.](./media/23_rev-rec-scenarios.png)](./media/23_rev-rec-scenarios.png)

Quindi, aprire la pagina **Tutti i clienti** (**Contabilità clienti \> Clienti \> Tutti i clienti**), selezionare il cliente **US\_SI\_0003** e quindi selezionare **Transazioni**. Verrà visualizzata la fattura aperta dell'ordine cliente 000036. Se si seleziona il giustificativo, viene visualizzata la voce contabile originale, non la nuova voce contabile della riallocazione. La voce di storno e la nuova voce contabile non possono essere visualizzate dalla contabilità clienti.

Il secondo ordine cliente è ora fatturato. La fattura totale presentata al cliente è per $1.099,00 + $71,44 imposta = $1.170,44. La figura seguente mostra la voce contabile registrata.

[![Pagina Transazioni giustificativo con la voce contabile registrata.](./media/24_rev-rec-scenarios.png)](./media/24_rev-rec-scenarios.png)

Poiché la somma dei ricavi e delle vendite è superiore a $1.170,44, la differenza viene registrata per -$130,17. Questo importo compensa il saldo dal conto di compensazione parziale dei ricavi fattura. Tale saldo viene registrato nella nuova voce contabile dopo la riallocazione.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
