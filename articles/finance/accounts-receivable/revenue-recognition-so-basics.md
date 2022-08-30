---
title: Riconoscimento ricavi negli ordini cliente
description: In questo articolo viene descritta la funzionalità di base per il riconoscimento ricavi negli ordini cliente e nelle fatture. Il riconoscimento ricavi è disponibile nell'ordine cliente e nella fattura corrispondente creata dall'ordine cliente.
author: bking
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: bking
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: bb031b41c07aaff06b41830fb0c322503e9f27ec
ms.sourcegitcommit: 1909d18a74cef85aad020a6a7473281e451f58c7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2022
ms.locfileid: "9348240"
---
# <a name="revenue-recognition-on-sales-orders"></a>Riconoscimento ricavi negli ordini cliente

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Il riconoscimento ricavi non può essere attivato tramite Gestione funzionalità. Per attivarlo, attualmente è necessario utilizzare le chiavi di configurazione.

In questo articolo viene descritta la funzionalità di base per il riconoscimento ricavi negli ordini cliente e nelle fatture. Il riconoscimento ricavi è disponibile in un ordine cliente e nella fattura corrispondente creata dall'ordine cliente. L'ordine cliente può anche essere creato con un progetto di tempistica e materiali.

> [!NOTE]
> Nelle figure di questo articolo, le colonne sono state nascoste o aggiunte alle griglie per una migliore visualizzazione dei concetti. Di conseguenza, le pagine e i dati contenuti nelle figure possono essere diversi da quanto viene visualizzato nel prodotto.

## <a name="enter-a-sales-order"></a>Inserire un ordine cliente

È stato inserito il seguente ordine cliente, che comprende tre articoli impostati per il riconoscimento ricavi.

[![Inserire un ordine cliente.](./media/revenue-recognition-so-basic-sales-order-header.png)](./media/revenue-recognition-so-basic-sales-order-header.png)

Sono disponibili due concetti per il riconoscimento ricavi:

- **Determinare il prezzo dei ricavi.** Il prezzo dei ricavi viene calcolato in base alle impostazioni dei prodotti rilasciati. Il prezzo dei ricavi non è mai mostrato al cliente, ma viene utilizzato solo per la contabilità della fattura ordine cliente. Le righe ordine cliente e i documenti stampati durante la vendita continuano a riportare il prezzo unitario/di listino.
- **Determinare se deve essere eseguito il riconoscimento ricavi.** Per determinare quando riconoscere i ricavi viene utilizzata una programmazione dei ricavi.

    In questo esempio, il primo articolo, S0001, è assegnato a una programmazione dei ricavi **1O** (singola occorrenza). Questa riga rappresenta uno scenario di riferimento in cui i ricavi vengono riconosciuti dopo la futura installazione. Di conseguenza, i ricavi vengono differiti fino al completamento dell'installazione.

    Il secondo articolo, S0008, è un articolo di tipo Assistenza impostato come articolo di supporto contratti registrati (PCS). I servizi di progettazione supportati vengono forniti al cliente per un periodo di 12 mesi. Di conseguenza, al prodotto viene assegnata una programmazione dei ricavi di **12M** per impostazione predefinita. Poiché l'articolo è di tipo PCS, occorre definire la data di inizio e fine del contratto. Per impostazione predefinita, le date di inizio e fine del contratto sono indicate nella scheda Impostazioni dei dettagli articolo. Nella programmazione dei ricavi viene specificata l'impostazione di **12M** in modo da inserire automaticamente i termini del contratto, come illustrato nella figura seguente.

    [![Programmazione dei ricavi.](./media/revenue-recognition-so-basic-revenue-schedules.png)](./media/revenue-recognition-so-basic-revenue-schedules.png)

    Il terzo articolo, S0012, è di tipo hardware e per impostazione predefinita non viene assegnata alcuna programmazione dei ricavi. I ricavi per i componenti hardware vengono riconosciuti dopo la fatturazione dell'articolo.

## <a name="confirm-the-sales-order"></a>Confermare l'ordine cliente

Per visualizzare ulteriori dettagli relativi al prezzo e alla programmazione dei ricavi, utilizzare i pulsanti nel gruppo **Riconoscimento ricavi** nella scheda **Gestisci** nel riquadro Azioni dell'ordine cliente. Poiché in questa fase l'ordine cliente non è confermato, i pulsanti utilizzati per il riconoscimento ricavi non sono disponibili. Questi pulsanti diventano disponibili o non disponibili durante l'elaborazione dell'ordine cliente fino alla fase di evasione.

[![Intestazione ordine cliente.](./media/revenue-recognition-so-basic-sales-order-header-02.png)](./media/revenue-recognition-so-basic-sales-order-header-02.png)

I primi tre pulsanti forniscono dettagli relativi al prezzo dei ricavi per gli articoli nell'impostazione ordini cliente per il riconoscimento ricavi.

- **Allocazione del prezzo dei ricavi**: questo pulsante diventa disponibile dopo aver confermato l'ordine cliente o registrato la fattura. Sia la conferma dell'ordine cliente che la registrazione della fattura consentono di calcolare i ricavi per il riconoscimento del prezzo che verrà rilevato o differito nella voce contabile. A seconda delle impostazioni, il prezzo dei ricavi calcolato può essere diverso dal prezzo unitario mostrato al cliente.
- **Riallocazione del prezzo con nuove righe ordine**: questo pulsante diventa disponibile dopo aver confermato l'ordine cliente o registrato la fattura. Il processo di riallocazione viene utilizzato per ricalcolare i ricavi che devono essere riconosciuti dopo aver aggiunto una nuova riga nell'ordine cliente corrente, in seguito a fatturazione o in un nuovo ordine cliente. In entrambi gli scenari, l'aggiunta di un nuovo articolo apporta una modifica al contratto. Di conseguenza, il prezzo dei ricavi deve essere riallocato.
- **Aggiornamento dell'allocazione del prezzo dei ricavi**: questo pulsante diventa disponibile dopo aver confermato l'ordine cliente, ma non è più disponibile dopo la fatturazione. L'aggiornamento viene utilizzato per rieseguire l'allocazione del prezzo dei ricavi senza dover confermare l'ordine cliente. Dopo aver fatturato l'ordine cliente, il prezzo dei ricavi non può essere ricalcolato.

Gli ultimi due pulsanti forniscono dettagli relativi alla programmazione dei ricavi per gli articoli dell'ordine cliente con una programmazione dei ricavi.

- **Programmazione prevista del riconoscimento ricavi**: questo pulsante diventa disponibile dopo aver confermato l'ordine cliente, ma non è più disponibile dopo la fatturazione. Si apre una pagina in cui viene visualizzata la programmazione dei ricavi prevista. La programmazione finale può cambiare poiché la programmazione prevista utilizza la data di spedizione richiesta, mentre la programmazione finale utilizza la data di spedizione effettiva.
- **Programmazione del riconoscimento ricavi**: questo pulsante diventa disponibile dopo aver fatturato l'ordine cliente. La programmazione finale del riconoscimento ricavi non viene creata al momento della conferma o alla creazione di un documento di trasporto. Viene creata solo al momento della fatturazione dell'ordine cliente.

Nell'esempio seguente, l'allocazione del prezzo dei ricavi si verifica alla conferma dell'ordine cliente. Anche se i prezzi dei ricavi vengono allocati in modo diverso, l'importo totale nel campo **Ricavi da riconoscere** deve essere comunque pari alla somma delle righe ordine cliente fatturate al cliente. Ad esempio, la somma delle righe ordine cliente, IVA esclusa, è pari a $1.499. Di conseguenza, anche la somma dei valori **Ricavi da riconoscere** deve essere pari a $ 1.499.

[![Allocazione del prezzo dei ricavi.](./media/revenue-recognition-so-basic-revenue-price-allocation.png)](./media/revenue-recognition-so-basic-revenue-price-allocation.png)

Viene creata anche la programmazione prevista del riconoscimento ricavi. La programmazione dei ricavi utilizza il valore **Ricavi da riconoscere** come importo da differire. Nell'articolo S0001 vengono differiti $321,21 anziché $300 e nell'articolo S0008 vengono differiti $160,61 anziché $100. L'articolo S0012 non viene visualizzato nella programmazione prevista poiché i ricavi non sono stati differiti. Al momento della registrazione, nell'articolo S0012 vengono registrati $ 1.017,18 direttamente nel conto CoGe dei ricavi.

[![Programmazione prevista del riconoscimento ricavi.](./media/revenue-recognition-so-basic-expected-rev-rec-schedule.png)](./media/revenue-recognition-so-basic-expected-rev-rec-schedule.png)

## <a name="create-the-packing-slip"></a>Creare il documento di trasporto

A questo punto, il documento di trasporto può essere creato per l'ordine cliente. I ricavi non vengono riconosciuti alla registrazione del documento di trasporto. Se l'ordine cliente non è stato confermato, la registrazione del documento di trasporto non attiva il calcolo dei prezzi dei ricavi. Neanche la programmazione prevista o finale del riconoscimento ricavi viene attivata. Se il gruppo di modelli di articoli è impostato in modo tale da differire i ricavi nel documento di trasporto, la registrazione continuerà a essere effettuata tramite i conti CoGe del profilo di registrazione corrente, anziché tramite i nuovi conti ricavi differiti che vengono utilizzati nella registrazione della fattura.

## <a name="create-the-invoice"></a>Creare la fattura

L'ultimo passaggio consiste nella fatturazione dell'ordine cliente. Considerando il giustificativo della fattura, si nota che i ricavi per gli articoli S0001 e S0008 sono stati differiti ($321,21 + 160,61 = 481,82) e che l'importo rimanente per l'articolo S0012 è stato registrato nei ricavi (1.017,18). Questi valori si aggiungono all'importo di $ 1.499, che corrisponde alla somma delle righe ordine cliente.

[![Transazioni giustificativo.](./media/revenue-recognition-so-voucher-transactions.png)](./media/revenue-recognition-so-voucher-transactions.png)

Dopo aver creato la fattura, diventano disponibili i pulsanti **Allocazione del prezzo dei ricavi**, **Riallocazione del prezzo con nuove righe ordine** e **Programmazione del riconoscimento ricavi** per la funzionalità di riconoscimento ricavi, ma i pulsanti **Aggiornamento dell'allocazione del prezzo dei ricavi** e **Programmazione prevista del riconoscimento ricavi** non sono disponibili.

[![Disponibilità del pulsante per il riconoscimento ricavi.](./media/revenue-recognition-so-basic-after-invoice-buttons.png)](./media/revenue-recognition-so-basic-after-invoice-buttons.png)

Il pulsante **Allocazione del prezzo dei ricavi** è ancora disponibile per visualizzare il calcolo del prezzo dei ricavi. Se dopo la conferma dell'ordine cliente non si è verificata alcuna variazione, la registrazione della fattura non modifica l'importo calcolato nel campo **Ricavi da riconoscere**.

La programmazione prevista del riconoscimento ricavi viene rimossa e sostituita con la programmazione finale del riconoscimento ricavi. I dettagli della programmazione dei ricavi vengono gestiti per ogni riga ordine cliente e utilizzati per rilasciare i ricavi differiti sui ricavi effettivi quando gli obblighi contrattuali sono soddisfatti.

[![Programmazione finale del riconoscimento ricavi.](./media/revenue-recognition-so-revenue-recognition-schedule.png)](./media/revenue-recognition-so-revenue-recognition-schedule.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
