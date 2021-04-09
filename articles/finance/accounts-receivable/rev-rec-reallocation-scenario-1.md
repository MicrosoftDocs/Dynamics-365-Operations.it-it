---
title: Riallocazione del riconoscimento ricavi - Scenario 1
description: Questo argomento descrive uno scenario di riallocazione in cui vengono immessi due ordini cliente solo confermati. Lo stesso scenario produrrà risultati simili se più di due ordini cliente sono nello stato confermato.
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
ms.openlocfilehash: f94b054d213dc2b347f4e5a7b2f4c2a51d519f57
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5824006"
---
# <a name="revenue-recognition-reallocation--scenario-1"></a>Riallocazione del riconoscimento ricavi - Scenario 1

[!include [banner](../includes/banner.md)]

Questo argomento descrive uno scenario di riallocazione in cui vengono immessi due ordini cliente solo confermati. Lo stesso scenario produrrà risultati simili se più di due ordini cliente sono nello stato confermato.

Per questo scenario, l'opzione **Correzioni delle fatture registrate in contabilità clienti** è impostata su **No** nella scheda **Riconoscimento ricavi** della pagina **Parametri di contabilità generale** (**Riconoscimento ricavi \> Impostazione \> Parametri di contabilità generale**).

[![Opzione Correzioni delle fatture registrate in contabilità clienti impostata su No](./media/06_rev-rec-scenarios.png)](./media/06_rev-rec-scenarios.png)

Viene creato un ordine cliente per il cliente US\_SI\_0003. Il cliente acquista un laptop (numero articolo S0012) e un piano di supporto (numero articolo S0008, "Sustained Engineering Service"). I ricavi per il laptop vengono riconosciuti immediatamente (non esiste un programma di riconoscimento dei ricavi). I ricavi per il piano di supporto saranno differiti e riconosciuti su 12 mesi, come definito dall'intervallo di date nel contratto.

[![Righe ordine cliente per il laptop e il piano di supporto](./media/07_rev-rec-scenarios.png)](./media/07_rev-rec-scenarios.png)

L'ordine cliente è confermato. Poiché entrambi gli articoli sono impostati per l'allocazione dei prezzi dei ricavi, il prezzo dei ricavi viene calcolato quando l'ordine cliente viene confermato. È possibile visualizzare i ricavi che verranno riconosciuti nella pagina **Allocazione del prezzo dei ricavi** (andare alla pagina **Ordine cliente**, riquadro Azioni, scheda **Gestisci**, gruppo **Riconoscimento dei ricavi** e selezionare **Allocazione del prezzo dei ricavi**). I ricavi per il laptop verranno registrati nel conto ricavi per un importo di $1.008,01. I ricavi per il piano di supporto verranno registrati nel conto ricavi differiti per un importo di $190,99. La somma dei prezzi dei ricavi deve essere uguale alla somma delle righe impostate per acquisire l'allocazione dei prezzi dei ricavi ($1.199,00).

[![Pagina Allocazione del prezzo dei ricavi](./media/08_rev-rec-scenarios.png)](./media/08_rev-rec-scenarios.png)

Il cliente ha scelto di non acquistare i servizi di installazione (numero articolo S0001) al momento della vendita, ma in seguito ha cambiato idea. Di conseguenza, viene immesso un secondo ordine cliente per lo stesso cliente.

[![Riga ordine cliente per servizi di installazione](./media/09_rev-rec-scenarios.png)](./media/09_rev-rec-scenarios.png)

Il secondo ordine cliente è confermato. Poiché questo ordine cliente contiene solo una riga, l'allocazione del prezzo dei ricavi non viene eseguita quando l'ordine cliente viene confermato. L'allocazione del prezzo dei ricavi si verifica solo se sono presenti due o più articoli univoci e se tali articoli sono impostati per l'allocazione dei prezzi dei ricavi.

Se questo nuovo ordine cliente è l'unica modifica al contratto del cliente, il processo di riallocazione può ora essere eseguito. In uno dei due ordini cliente selezionare **Riallocazione del prezzo con nuove righe ordine** per aprire la pagina **Riallocazione del prezzo con nuove righe ordine**. In alternativa, andare a **Riconoscimento dei ricavi \> Attività periodiche \> Riallocazione del prezzo con nuove righe ordine**. Selezionare i due ordini cliente e le righe corrispondenti, quindi scegliere **Aggiorna riallocazione**. La colonna **Importo riallocato** mostra il nuovo prezzo dei ricavi per ogni riga dell'ordine cliente.

[![Nuovi prezzi dei ricavi nella pagina Riallocazione del prezzo con nuove righe ordine](./media/10_rev-rec-scenarios.png)](./media/10_rev-rec-scenarios.png)

Se si seleziona **Giustificativo previsto**, non viene visualizzato nulla perché non sono state registrate fatture.

Per completare la riallocazione, selezionare **Processo**. Viene richiesta una data di registrazione, anche se non viene registrato nulla. Una volta completata la riallocazione, la pagina **Allocazione del prezzo dei ricavi** per ogni ordine cliente mostrerà l'allocazione dei prezzi per tutti gli articoli in entrambi gli ordini cliente. In altre parole, la pagina **Allocazione del prezzo dei ricavi** per ogni ordine cliente includerà un articolo che non esiste in quell'ordine cliente perché fa parte dello stesso contratto ma in un ordine cliente diverso.

> [!TIP]
> Per fornire un contesto sul motivo per cui vengono visualizzati questi elementi aggiuntivi, è possibile aggiungere altre colonne alla griglia, ad esempio **ID riallocazione** e **Ordine cliente**.
> 
> [![Colonne aggiuntive nella pagina Allocazione del prezzo dei ricavi](./media/11_rev-rec-scenarios.png)](./media/11_rev-rec-scenarios.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]