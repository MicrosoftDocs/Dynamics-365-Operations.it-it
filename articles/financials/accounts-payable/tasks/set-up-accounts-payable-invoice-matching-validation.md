--- 
title: "Impostare la convalida dell'abbinamento fatture della contabilità fornitori"
description: "Questa registrazione utilizza la società dimostrativa USMF."
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 7a26a057b524f162e4b288b88e8c30f7c5db7a45
ms.contentlocale: it-it
ms.lasthandoff: 10/16/2018

---
# <a name="set-up-accounts-payable-invoice-matching-validation"></a>Impostare la convalida dell'abbinamento fatture della contabilità fornitori

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa registrazione utilizza la società dimostrativa USMF. Il ruolo di responsabile della contabilità fornitori o del responsabile della contabilità eseguirebbe le operazioni. Prima di iniziare, assicurarsi che sia selezionata la chiave di configurazione Abbinamento fatture. Se la persona giuridica tiene traccia delle spese, ad esempio di trasporto, tramite le spese varie, verificare che sia selezionata la chiave di configurazione Spese.  Il processo di abbinamento fatture della contabilità fornitori consente di abbinare le informazioni relative a fatture fornitore, ordini fornitore ed entrate prodotti. Le differenze tra questi documenti sono dette discrepanze di abbinamento. Le discrepanze di abbinamento vengono confrontate con le tolleranze specificate. Se una discrepanza di abbinamento supera la percentuale o l'importo di tolleranza, nei moduli Fattura fornitore e Dettagli abbinamento fatture verranno visualizzate icone di scostamento relative all'abbinamento.

1. Andare a Contabilità fornitori > Impostazioni > Parametri contabilità fornitori.
2. Fare clic sulla scheda Convalida fattura.
3. Selezionare o deselezionare la casella di controllo Abilita convalida abbinamento fatture.
    * Specificare se deve essere richiesta un'approvazione prima di registrare una fattura contenente discrepanze di abbinamento fatture. Se questo è impostato su Consenti con avviso, verrà visualizzata un'indicazione visiva quando una discrepanza di abbinamento fatture supera la tolleranza. Tuttavia, sarà possibile registrare la fattura. Per utilizzare i flussi di lavoro insieme alla convalida di abbinamento fatture, verificare che il campo Registra fatture con discrepanze sia impostato su Consenti con avviso per evitare di dover approvare più volte.  
    * Nel campo Aggiorna automaticamente lo stato dell'intestazione fattura selezionare se l'abbinamento verrà eseguito automaticamente durante l'immissione dati della fattura dal sistema. L'impostazione consigliata è Sì, a meno che non si verifichino problemi relativi alle prestazioni dell'immissione dati. La disattivazione degli aggiornamenti automatici potrebbe consentire prestazioni di sistema più veloci poiché la convalida dell'abbinamento fatture verrà ignorata durante l'immissione dei dati. Un addetto all'immissione dati dovrà manualmente aggiornare lo stato di abbinamento della fattura per visualizzare i risultati della convalida dell'abbinamento fatture quando questo è impostato su No.  
4. Attiva/disattiva l'espansione della sezione Abbinamento totali fatture.
5. Selezionare o deselezionare la casella di controllo Abbina totali fatture per abbinare i totali fatture effettivi con i totali previsti.
    * Specificare se visualizzare un'icona nel caso in cui una discrepanza di abbinamento fatture superi la tolleranza. È possibile specificare di visualizzare l'icona se una discrepanza positiva supera la tolleranza oppure se una discrepanza positiva o negativa supera la tolleranza.  
    * Ad esempio, la tolleranza è del 5% e l'importo fattura totale dell'ordine fornitore è 100,00. Di conseguenza, se l'importo totale della fattura supera 105,00 verrà visualizzata un'icona di abbinamento prezzo. Se si seleziona Se il valore è maggiore o minore della tolleranza, verrà visualizzata l'icona anche nel caso in cui l'importo della fattura sia inferiore a 95,00.  
6. Nel campo Percentuale di tolleranza totali fatture immettere un numero.
7. Attiva/disattiva l'espansione della sezione Abbinamento prezzo e quantità.
    * Nel campo Criteri di abbinamento riga selezionare un valore da utilizzare come criterio predefinito per la persona giuridica che si sta utilizzando. "Non obbligatorio" significa non è necessaria alcuna verifica dei prezzi delle singole righe della fattura rispetto al prezzo dell'ordine fornitore alle quantità della fattura o del documento di trasporto. L'"Abbinamento a due elementi di verifica" indica che la verifica delle righe fattura è richiesta ma solo l'ordine fornitore e i documenti relativi alla fattura fornitore sono compresi nella verifica. L'entrata prodotti non viene considerata nelle convalide di abbinamento. L'"Abbinamento a tre elementi di verifica" indica che il prezzo unitario netto verrà confrontato con il prezzo unitario netto dell'ordine fornitore e la quantità dell'entrata prodotti corrispondente verrà confrontata con la quantità della fattura.  
    * Se si utilizzano criterio di abbinamento riga a due o a tre elementi di verifica, è possibile impostare le percentuali di tolleranza prezzi per i la persona giuridica, gli articoli e i fornitori nella pagina di tolleranza prezzi articolo. Quando le fatture fornitore vengono confrontate con le informazioni relative agli ordini fornitore, viene cercata la percentuale di tolleranza prezzi applicabile.  
8. Nel campo Criteri di abbinamento riga selezionare un'opzione.
    * Per consentire un livello di abbinamento diverso da applicare per un articolo, un fornitore, una combinazione di articolo e fornitore o una riga ordine fornitore, selezionare un valore nel campo Consenti di ignorare i criteri di abbinamento. I criteri di abbinamento riga della persona giuridica possono essere ignorati per un fornitore, un articolo o una combinazione di articolo e fornitore specifici nella pagina Criteri di abbinamento.  
    * Per abbinare i totali dei prezzi per le voci delle fatture, selezionare un valore nel campo Associa prezzi totali. Questo tipo di abbinamento è utile quando il fornitore invia più fatture per la stessa riga ordine fornitore. È possibile confrontare le informazioni sul prezzo per l'importo netto di ogni riga fattura e tutte le righe fattura precedentemente registrate e in sospeso, con l'importo netto della riga ordine fornitore corrispondente.  
9. Nel campo Associa prezzi totali selezionare un'opzione.
10. Nel campo Tolleranza del prezzo di acquisto totale immettere un numero.
11. Attiva/disattiva l'espansione della sezione Abbinamento spese.
12. Selezionare la casella di controllo Abbina spese per abbinare le spese effettive con le spese previste, in base alle informazioni sull'ordine fornitore.
13. Chiudere la pagina.


