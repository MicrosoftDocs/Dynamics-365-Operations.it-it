---
title: Impostare la convalida dell'abbinamento fatture Contabilità fornitori
description: In questo argomento vengono fornite informazioni su come impostare la convalida dell'abbinamento fatture Contabilità fornitori.
author: abruer
manager: AnnBe
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendParameters
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 662b080a0e87ae6ce7d89ffa848579517dd9b6a8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4979240"
---
# <a name="set-up-accounts-payable-invoice-matching-validation"></a>Impostare la convalida dell'abbinamento fatture Contabilità fornitori

[!include [banner](../../includes/banner.md)]

Prima di iniziare, assicurarsi che sia selezionata la chiave di configurazione Abbinamento fatture. Se la persona giuridica tiene traccia delle spese, ad esempio di trasporto, tramite le spese varie, verificare che sia selezionata la chiave di configurazione Spese.  Il processo di abbinamento fatture Contabilità fornitori consente di abbinare le informazioni relative a fatture fornitore, ordini fornitore ed entrate prodotti. Le differenze tra questi documenti sono dette discrepanze di abbinamento. Le discrepanze di abbinamento vengono confrontate con le tolleranze specificate. Se una discrepanza di abbinamento supera la percentuale o l'importo di tolleranza, nelle pagine **Fattura fornitore** e **Dettagli abbinamento fatture** verranno visualizzate icone di scostamento abbinamento.

## <a name="determine-which-invoice-matching-validation-to-use"></a>Determinare la convalida dell'abbinamento fatture da utilizzare
Sono disponibili quattro diversi tipi di convalida dell'abbinamento. 

- **Abbinamento a livello di riga**: il tipo di abbinamento più comune è l'abbinamento riga. L'abbinamento a livello di riga può essere un abbinamento a due o a tre elementi di verifica. L'abbinamento a livello di riga predefinito può essere specificato per una persona giuridica nella pagina **Parametro contabilità fornitori**. L'abbinamento a due elementi di verifica confronta il prezzo unitario presente nella fattura a quello presente nell'ordine fornitore. L'abbinamento a tre elementi di verifica confronta anche la quantità in fattura alla quantità dell'entrata prodotti abbinata.
- **Abbinamento totali fatture**: consente di abbinare gli importi totali della fattura agli importi totali dell'ordine fornitore. Questo tipo di abbinamento fatture include il livello minimo di dettaglio, questa opzione può essere utilizzata per ridurre al minimo il tempo impiegato dal personale per la verifica delle informazioni di abbinamento fatture. Vengono confrontati sei totali, tra cui Subtotale, Sconto totale, Spese, IVA, Arrotondamento e Importo fattura. Il sistema verificherà se uno qualsiasi di questi valori nella fattura devia dagli importi previsti oltre uno scostamento accettabile.
- **Abbinamento spese**: consente di abbinare le informazioni sulle spese (importi) presenti nella fattura alle informazioni sulle spese (importi) presenti nell'ordine fornitore.
- **Totali prezzo per abbinamento voci riga**: questo tipo di abbinamento è utile per le società che in genere ricevono più fatture per una singola riga di ordine fornitore. Se in genere si riceve una sola fattura per riga di ordine fornitore, questo tipo di abbinamento non è necessario. Questo abbinamento richiede l'attivazione dell'abbinamento a due o tre elementi di verifica e viene utilizzato come convalida dell'importo netto da non superare, in base alle percentuali e agli importi di tolleranza.  Questo tipo di abbinamento confronta le informazioni sul prezzo per l'importo netto di ogni riga fattura e tutte le righe fattura precedentemente registrate e in sospeso, con l'importo netto della riga ordine fornitore corrispondente. L'importo netto viene determinato in base alla formula seguente: (prezzo unitario * quantità riga) + spese riga - sconti riga. Quando si abbinano i prezzi totali in base alla percentuale, il sistema confronta i valori utilizzando la valuta della transazione. Quando si abbinano i prezzi totali in base all'importo, il sistema confronta i valori utilizzando la valuta di contabilizzazione.

## <a name="set-up-parameters-to-enable-invoice-matching-validation"></a>Impostare i parametri per abilitare la convalida dell'abbinamento fatture
1. Passare a **Contabilità fornitori > Impostazione > Parametri contabilità fornitori**.
2. Selezionare la scheda **Convalida fattura**.
3. Selezionare o deselezionare la casella di controllo **Abilita convalida abbinamento fatture**.
    * Specificare se deve essere richiesta un'approvazione prima di registrare una fattura contenente discrepanze di abbinamento fatture. Se impostato su **Consenti con avviso**, verrà visualizzata un'indicazione visiva quando una discrepanza di abbinamento fatture supera la tolleranza. Tuttavia, sarà possibile registrare la fattura. Per utilizzare i flussi di lavoro insieme alla convalida di abbinamento fatture, verificare che il campo **Registra fatture con discrepanze** sia impostato su **Consenti con avviso** per evitare di dover approvare più volte.  
    * Nel campo **Aggiorna automaticamente lo stato dell'intestazione fattura** selezionare se l'abbinamento verrà eseguito automaticamente durante l'immissione dati della fattura dal sistema. L'impostazione consigliata è **Sì**, a meno che non si verifichino problemi relativi alle prestazioni dell'immissione dati. La disattivazione degli aggiornamenti automatici potrebbe consentire prestazioni di sistema più veloci poiché la convalida dell'abbinamento fatture verrà ignorata durante l'immissione dei dati. Un addetto all'immissione dati dovrà manualmente aggiornare lo stato di abbinamento della fattura per visualizzare i risultati della convalida dell'abbinamento fatture quando questo è impostato su **No**.  
4. Impostare **Abbinamento totali fatture**.
5. Selezionare o deselezionare la casella di controllo **Abbina totali fatture** per abbinare i totali fatture effettivi con i totali previsti.
    * Specificare se visualizzare un'icona nel caso in cui una discrepanza di abbinamento fatture superi la tolleranza. È possibile specificare di visualizzare l'icona se una discrepanza positiva supera la tolleranza oppure se una discrepanza positiva o negativa supera la tolleranza.  
    * Ad esempio, la tolleranza è del 5% e l'importo fattura totale dell'ordine fornitore è 100,00. Di conseguenza, se l'importo totale della fattura supera 105,00 verrà visualizzata un'icona di abbinamento prezzo. Se si seleziona **Se il valore è maggiore o minore della tolleranza**, verrà visualizzata l'icona anche nel caso in cui l'importo della fattura sia inferiore a 95,00.  
6. Nel campo **Percentuale di tolleranza totali fatture**, immettere lo scostamento percentuale accettabile. Questo valore è il valore predefinito per la società. Questo valore può essere sostituito per specifici fornitori, utilizzando la pagina **Tolleranze totali fatture**. Per informazioni su come sostituire la percentuale di tolleranza dei totali fattura per uno specifico fornitore, vedere la sezione "Impostare la tolleranza di abbinamento dei totali fattura per i fornitori" più avanti in questo argomento.
7. Impostare **Abbinamento prezzo e quantità**.
8. Nel campo **Criteri di abbinamento riga** selezionare un valore da utilizzare come criterio predefinito per la persona giuridica che si sta utilizzando. **Non obbligatorio** significa non è necessaria alcuna verifica dei prezzi delle singole righe della fattura rispetto al prezzo dell'ordine fornitore alle quantità della fattura o del documento di trasporto. **Abbinamento a due elementi** indica che la verifica delle righe fattura è richiesta ma solo l'ordine fornitore e i documenti relativi alla fattura fornitore sono compresi nella verifica. L'entrata prodotti non viene considerata nelle convalide di abbinamento. **Abbinamento a tre elementi** indica che il prezzo unitario netto verrà confrontato con il prezzo unitario netto dell'ordine fornitore e la quantità dell'entrata prodotti corrispondente verrà confrontata con la quantità della fattura.
9. Per consentire un livello di abbinamento diverso da applicare per un articolo, un fornitore, una combinazione di articolo e fornitore o una riga ordine fornitore, selezionare un valore nel campo **Consenti di ignorare i criteri di abbinamento**. I criteri di abbinamento riga della persona giuridica possono essere ignorati per un fornitore, un articolo o una combinazione di articolo e fornitore specifici nella pagina **Criteri di abbinamento**.
    * Se si utilizzano criteri di abbinamento riga a due o a tre elementi di verifica, è possibile impostare le percentuali di tolleranza dei prezzi per la persona giuridica, gli articoli e i fornitori nella pagina di **tolleranza prezzi articolo**. La tolleranza prezzi predefinita della persona giuridica verrà impostata sulla percentuale zero per l'abbinamento a due e a tre elementi di verifica. Quando le fatture fornitore vengono confrontate con le informazioni relative agli ordini fornitore, viene cercata la percentuale di tolleranza dei prezzi applicabile.   
10. Per abbinare i totali dei prezzi per le voci delle fatture, selezionare un valore nel campo **Associa prezzi totali**. Questo tipo di abbinamento è utile quando il fornitore invia più fatture per la stessa riga ordine fornitore. È possibile confrontare le informazioni sul prezzo per l'importo netto di ogni riga fattura e tutte le righe fattura precedentemente registrate e in sospeso, con l'importo netto della riga ordine fornitore corrispondente.  Le opzioni disponibili sono **Nessuno**, **Percentuale**, **Importo** o **Percentuale e importo**.
11. Nel campo **Percentuale di tolleranza del prezzo di acquisto totale**, immettere una percentuale di scostamento accettabile. Questo campo è disponibile quando **Associa prezzi totali** è impostato su **Percentuale** o **Percentuale e importo**.
12. Nel campo **Tolleranza del prezzo di acquisto totale**, immettere un importo nella valuta di contabilizzazione. Questo campo è disponibile quando **Associa prezzi totali** è impostato su **Importo** o **Percentuale e importo**.
13. Nel campo **Visualizza icona abbinamento del prezzo totale**, specificare quando visualizzare un'icona nel caso in cui una discrepanza di abbinamento fatture superi la tolleranza relativa al prezzo netto unitario. L'icona può essere visualizzata nel caso in cui una discrepanza positiva superi la tolleranza oppure una discrepanza positiva o negativa superi la tolleranza.
Ad esempio, la tolleranza è del 5% e il totale prezzo della riga dell'ordine fornitore è 10,00. Di conseguenza, se il totale prezzo riga della fattura supera 10,50 verrà visualizzata un'icona di abbinamento prezzo. Se si seleziona **Se il valore è maggiore o minore della tolleranza**, verrà visualizzata l'icona anche nel caso in cui il totale prezzo riga nella fattura è inferiore a 9,50.
13. Impostare l'abbinamento spese.
14. Selezionare la casella di controllo **Abbina spese** per abbinare le spese effettive con le spese previste, in base alle informazioni sull'ordine fornitore.

## <a name="set-up-unit-price-tolerance-percentages"></a>Impostare le percentuali di tolleranza dei prezzi unitari
Passare a **Contabilità fornitori > Impostazioni > Impostazione abbinamento fatture > Tolleranze prezzi** per definire le percentuali di tolleranza dei prezzi. Se si utilizzano criteri di abbinamento riga a due o a tre elementi di verifica, è possibile impostare le percentuali di tolleranza prezzi per la persona giuridica, gli articoli e i fornitori. Quando le fatture fornitore vengono confrontate con le informazioni relative agli ordini fornitore, viene cercata la percentuale di tolleranza dei prezzi applicabile. L'ordine di ricerca predefinito è il seguente:
* Tabella/Tabella
* Tabella/Gruppo
* Tabella/Tutto
* Gruppo/Tabella
* Gruppo/Gruppo
* Gruppo/Tutto
* Tutto/Tabella
* Tutto/Gruppo
* Tutto/Tutto

La tolleranza prezzi predefinita della persona giuridica è 0% e viene applicata a tutti gli articoli e a tutti i conti (Tutti, Tutti). Il record della tolleranza prezzi predefinita della persona giuridica non può essere eliminato.

Per impostazione predefinita, sono consentite discrepanze di prezzo negative. Tuttavia, non è possibile immettere un numero negativo come percentuale di tolleranza dei prezzi. Per tenere traccia delle percentuali di tolleranza dei prezzi negativi, selezionare **Se il valore è maggiore o minore della tolleranza** nel campo **Visualizza icona abbinamento prezzi unitari** della pagina **Parametri contabilità fornitori**. Immettere quindi le percentuali di tolleranza dei prezzi nella pagina **Tolleranze prezzi**.

## <a name="set-up-matching-policy-override"></a>Impostare la sostituzione dei criteri di abbinamento

Passare **Contabilità fornitori > Impostazioni > Impostazione abbinamento fatture > Criteri di abbinamento** per definire il valore predefinito per il campo Criteri di abbinamento per le righe nel modulo Ordine fornitore. Questa impostazione è facoltativa. Utilizzare questo modulo per impostare l'abbinamento a due o a tre elementi di verifica per articoli, fornitori o combinazioni di fornitore e articolo. Queste voci consentono di definire i criteri di abbinamento più granulari dei criteri di abbinamento della persona giuridica definiti nella pagina **Parametri contabilità fornitori**. I criteri di abbinamento riga della persona giuridica predefinita si applicano a tutti gli articoli e ai fornitori, fatta eccezione per quelli per cui sono specificati criteri di abbinamento riga diversi in questa pagina.

In questa pagina, selezionare **Livello criteri di abbinamento**. Selezionare il livello della gerarchia dei criteri di abbinamento per impostare i criteri di abbinamento riga.

- **Articolo e fornitore**: specificare il criterio di abbinamento per gli articoli specifici acquistati da determinati fornitori.
- **Articolo**: specificare i criteri di abbinamento per specifici articoli acquistati da qualsiasi fornitore, eccetto quelli specificati a livello di articolo e fornitore.
- **Fornitore**: specificare i criteri di abbinamento per tutti gli articoli acquistati da specifici fornitori, eccetto quelli specificati a livello di articolo e di articolo e fornitore.
  
La gerarchia riportata di seguito viene utilizzata per determinare i criteri di abbinamento utilizzati:
  *  Articolo e fornitore
  *  Elemento
  *  Fornitore
  *  Persona giuridica
  
## <a name="set-up-invoice-totals-matching-tolerance-for-vendors"></a>Impostare la tolleranza di abbinamento totali fattura per i fornitori

Andare a **Contabilità fornitori > Impostazioni > Impostazione abbinamento fatture > Tolleranze totali fatture** per specificare le tolleranze specifiche dei fornitori per l'abbinamento dei totali fatture. Il calcolo di abbinamento utilizza la percentuale di tolleranza dei totali fatture del conto fornitore specificato come conto di ordine nella fattura fornitore. Se il conto fornitore non dispone di una percentuale di tolleranza specificata per i totali fattura, viene utilizzata la percentuale di tolleranza dei totali fattura specificata per la persona giuridica nella pagina **Parametri contabilità fornitori**.

1. Per specificare tolleranze per singoli fornitori che sostituiscano la tolleranza predefinita, selezionare un **Conto fornitore**.
2. Immettere la percentuale di scostamento accettata per questo fornitore.
