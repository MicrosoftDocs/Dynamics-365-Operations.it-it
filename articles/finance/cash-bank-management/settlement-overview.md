---
title: Panoramica della liquidazione
description: Questo argomento fornisce informazioni generali sul processo di liquidazione. Descrive i tipi di transazione che possono essere liquidati e i tempi e il processo necessari per la liquidazione. Viene anche fornita una descrizione dei risultati del processo di liquidazione.
author: panolte
ms.date: 07/30/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "14551"
- intro-internal
ms.assetid: 0968fa71-5984-415b-8689-759a0136d5d1
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 6b4a4fd0756a4516b0c14e136730d21d062a106a
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2021
ms.locfileid: "7344813"
---
# <a name="settlement-overview"></a>Panoramica della liquidazione

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


Questo argomento fornisce informazioni generali sul processo di liquidazione. Descrive i tipi di transazione che possono essere liquidati e i tempi e il processo necessari per la liquidazione. Viene anche fornita una descrizione dei risultati del processo di liquidazione.

Durante la compensazione, le transazioni in un documento vengono applicate alle transazioni in un altro documento per aumentare o diminuire il saldo di ciascun documento. È possibile ad esempio applicare un pagamento a una fattura. È possibile liquidare vari tipi di transazioni, in momenti diversi e con metodi diversi. Il processo di liquidazione può anche generare nuove transazioni.

## <a name="what-transactions-can-be-settled"></a>Quali transazioni possono essere compensate

In Contabilità fornitori e Contabilità clienti la liquidazione può verificarsi tra tipi di transazione che hanno impatto sul saldo fornitore o sul saldo cliente. Questi tipi di transazione possono includere fatture, pagamenti, note di credito e commissioni. Qualsiasi tipo di transazione può essere compensato a fronte di qualsiasi altro tipo di transazione. Ad esempio, è possibile liquidare un pagamento a fronte di una fattura, una nota di credito a fronte di una fattura, una fattura a fronte di un'altra fattura e un pagamento a fronte di un altro pagamento.

È possibile compensare pagamenti a fronte di una transazione nella stessa persona giuridica o in una persona giuridica diversa. Nelle organizzazioni che utilizzano un modello di pagamento centralizzato, i [pagamenti centralizzati](set-up-centralized-payments.md) possono semplificare il processo di pagamento.

## <a name="when-to-settle-transactions"></a>Quando compensare transazioni

Le transazioni possono essere liquidate quando vengono immessi i pagamenti. Ad esempio, quando si effettua un pagamento a un fornitore, in genere si selezionano le fatture da pagare. Selezionando le fatture, le transazioni vengono contrassegnate per la liquidazione a fronte del pagamento. Quando gli addetti ai pagamenti della contabilità clienti registrano i pagamenti dei clienti, è possibile contrassegnare le fatture appropriate per la liquidazione, in base alle informazioni incluse nel pagamento del cliente. Utilizzare la pagina **Liquida transazioni** per contrassegnare le transazioni per la liquidazione. È possibile aprire questa pagina da qualsiasi fattura o pagamento non registrato. Quando la transazione viene registrata, anche la liquidazione viene registrata. 

Le transazioni possono inoltre essere liquidate dopo la registrazione. È possibile immettere e registrare un pagamento cliente senza compensarlo a fronte di alcuna fattura. Tuttavia, è possibile che ci si voglia assicurare che il pagamento venga liquidato a fronte della fattura corretta prima di registrare la liquidazione. La pagina **Liquida transazioni** può essere aperta dalla pagina **Tutti i clienti** o **Tutti i fornitori** o dalla pagina **Transazioni** per qualsiasi cliente o fornitore.

È inoltre possibile prenotare pagamenti anticipati registrati per una fattura contrassegnando il pagamento per la compensazione a fronte di un ordine fornitore o un ordine cliente. In questo caso, il pagamento ha ancora un saldo aperto, ma non può essere liquidato a fronte di un'altra fattura. Il pagamento verrà automaticamente liquidato a fronte della fattura creata dall'ordine fornitore o dall'ordine cliente.

## <a name="how-to-settle-transactions"></a>Come compensare transazioni

Le transazioni possono essere compensate manualmente, automaticamente, o tramite una combinazione dei due metodi. La scelta di un metodo di liquidazione dipende dai processi aziendali. Nelle pagine **Parametri contabilità fornitori** e **Parametri contabilità clienti** è possibile configurare il processo di liquidazione in modo che sia allineato a tali processi aziendali.

È possibile creare i pagamenti fornitore e pagamenti in addebito diretto cliente utilizzando una proposta di pagamento. Una proposta di pagamento viene utilizzata per selezionare le fatture da pagare. La proposta di pagamento viene avviata manualmente, quindi il sistema contrassegna automaticamente le fatture selezionate per la liquidazione quando i pagamenti vengono creati.

Se i pagamenti vengono creati manualmente, è possibile utilizzare la pagina **Liquida transazioni** per selezionare le fatture per la liquidazione. È possibile selezionare manualmente le fatture, oppure utilizzare l'opzione **Contrassegna in base a priorità** per contrassegnare automaticamente le fatture per la liquidazione. L'opzione **Contrassegna in base a priorità** è disponibile solo per la contabilità clienti. È possibile attivare questa opzione nella scheda **Priorità di liquidazione** della pagina **Parametri contabilità clienti**.

Se un addetto al pagamento immette un pagamento ma non lo liquida prima di registrarlo, il pagamento può essere liquidato automaticamente. È possibile attivare la liquidazione automatica nelle pagine **Parametri contabilità clienti** e **Parametri contabilità fornitori**. La liquidazione automatica liquida le transazioni solo nella stessa persona giuridica. Non liquida le transazioni tra più persone giuridiche.

Quando si utilizza la liquidazione automatica, è possibile utilizzare la priorità di liquidazione predefinita oppure definire una priorità di liquidazione nella pagina **Parametri contabilità clienti**. Questa funzionalità è disponibile solo per la contabilità clienti.

## <a name="results-of-settlement"></a>Risultati della compensazione

Quando le transazioni vengono liquidate, il saldo scoperto di ciascuna transazione viene conseguentemente aumentato o diminuito. In genere, quando una fattura e un pagamento vengono liquidati, lo stato e il saldo di ciascuna transazione vengono aggiornati in base alle seguenti regole:

- Se l'importo del pagamento è superiore all'importo della fattura, il saldo della fattura viene ridotto a 0,00 e la fattura viene chiusa. Il pagamento rimarrà aperto e il saldo è la differenza tra importo del pagamento e importo della fattura.
- Se l'importo del pagamento è inferiore all'importo della fattura, il saldo del pagamento viene ridotto a 0,00 e il pagamento viene chiuso. La fattura rimarrà aperta e il saldo è la differenza tra importo della fattura e importo del pagamento.
- Se l'importo del pagamento è uguale all'importo della fattura, il pagamento e la fattura vengono entrambi chiusi e il saldo di entrambi è ridotto a 0,00.

Se l'[importo del pagamento è inferiore all'importo della fattura](../accounts-payable/vendor-payments-partial-amount.md) a causa di uno sconto di cassa, un annullamento o un pagamento insufficiente, la fattura e il pagamento potrebbero comunque venire chiusi, a seconda della configurazione della liquidazione nelle pagine **Parametri contabilità fornitori** e **Parametri di contabilità clienti**.

Le liquidazioni possono anche generare transazioni. Ad esempio, la liquidazione di una fattura e di un pagamento può produrre uno sconto di cassa, un profitto o una perdita realizzata, rettifiche di IVA, annullamenti o differenze in centesimi.

## <a name="identifying-marked-transactions-during-settlement"></a>Identificazione delle transazioni contrassegnate durante la liquidazione

Quando si tenta di liquidare una transazione, è possibile notare un simbolo che indica che la transazione è contrassegnata in un'altra posizione. In questo caso, è possibile selezionare la transazione nella pagina **Liquida transazioni** e quindi selezionare **Richiesta \> Liquidazione nella finestra di liquidazione**. La vista per questa richiesta mostra giornali di registrazione, ordini cliente, fatture, proposte di pagamento e posizioni dei clienti che potrebbero bloccare la liquidazione della transazione. Per risolvere il problema, è possibile selezionare il collegamento per passare direttamente dalla richiesta alla posizione bloccata. È quindi possibile aggiornare il documento con le rettifiche necessarie per la liquidazione. È anche possibile usare l'indicatore **Contrassegnato** per identificare altri documenti inclusi nella stessa posizione di blocco.

## <a name="resolve-issues-with-transactions-that-cant-be-settled"></a>Risolvere i problemi con le transazioni che non possono essere risolte

A volte, non è possibile regolare le transazioni perché un'altra attività sta elaborando il documento. Se si cerca di regolare le transazioni, si verifica un errore, perché quelle transazioni sono in uso. Per risolvere questo problema, puoi usare la pagina **dei dettagli delle transazioni mar** cate per trovare le transazioni marcate per il regolamento e identificare qualsiasi altro processo che vi sta accedendo.

Le transazioni sono segnate per il regolamento quando le fatture dei fornitori vengono pagate o quando i clienti pagano le loro fatture aperte. Occasionalmente, queste fatture potrebbero essere già segnate per il pagamento. Pertanto, gli utenti non possono selezionarli per il pagamento. Le fatture potrebbero essere contrassegnate da un altro giornale di pagamento del cliente, ordine di vendita, giornale di pagamento del fornitore o ordine di acquisto nell'entità legale corrente o in un'altra entità legale.

Se una transazione è bloccata per il regolamento quando si sta inserendo un pagamento del cliente, aprire la pagina dei **dettagli della transazione contrassegnata dal cliente** **(Accounts receivable \> Periodic tasks \> Customer marked transaction details**). Per identificare rapidamente dove una transazione è bloccata, è possibile impostare uno dei seguenti parametri di selezione: **Conto cliente**, **Buono**, **Data** o **Fattura**. Se non impostate alcun parametro di selezione, il sistema mostra tutti i documenti bloccati dell'azienda corrente o di un'altra azienda selezionata. Dopo aver identificato la transazione che è stata bloccata per il regolamento, è possibile selezionarla e poi selezionare **Deseleziona transazioni selezionate**. La transazione selezionata viene quindi rimossa da qualsiasi giornale che la include. Tuttavia, il documento non viene rimosso dall'altra posizione. Solo le informazioni di marcatura vengono rimosse da quel diario.

Se una transazione è bloccata per il regolamento quando si sta inserendo un pagamento di un fornitore, aprire la pagina dei **dettagli della transazione contrassegnata dal fornitore** **(Accounts payable \> Periodic tasks \> Vendor marked transaction details**). Per identificare rapidamente dove una transazione è bloccata, è possibile impostare uno dei seguenti parametri di selezione: **Conto del venditore**, **Buono**, **Data** o **Fattura**. Se non impostate alcun parametro di selezione, il sistema mostra tutti i documenti bloccati dell'azienda corrente o di un'altra azienda selezionata. Dopo che la transazione è stata identificata, puoi selezionarla e poi selezionare **Rimuovi contrassegno da transazioni selezionate** per risolvere il problema del blocco. La transazione selezionata viene poi rimossa da qualsiasi altro giornale in cui è stata selezionata. Tuttavia, il documento non viene rimosso dall'altra posizione. Solo le informazioni di marcatura vengono rimosse da quel diario.

Per identificare tutti i documenti bloccati, aprite la pagina dei **dettagli di tutte le transazioni marcate** **(Conti attivi \> Compiti periodici \> Tutti i dettagli delle transazioni marcate** o **Conti passivi \> Compiti periodici \> Tutti i dettagli delle transazioni marcate**). Per identificare rapidamente dove una transazione è bloccata, è possibile impostare uno dei seguenti parametri di selezione: **Conto cliente**, **conto venditore**, **buono**, **data** o **fattura**. Se non impostate alcun parametro di selezione, il sistema mostra tutti i documenti bloccati dell'azienda corrente o di un'altra azienda selezionata. Dopo che la transazione è stata identificata, puoi selezionarla e poi selezionare **Rimuovi contrassegno da transazioni selezionate** per risolvere il problema del blocco. La transazione selezionata viene poi rimossa da qualsiasi altro giornale in cui è stata selezionata. Tuttavia, il documento non viene rimosso dall'altra posizione. Solo le informazioni di marcatura vengono rimosse da quel diario.

Prima di poter utilizzare questa funzione, è necessario attivarla nel sistema. Gli amministratori possono utilizzare l'area di lavoro **Gestione funzionalità** per controllare lo stato della funzionalità e attivarla se necessario. Nell'area di lavoro, la funzionalità è elencata nel modo seguente:

- **Modulo:** Gestione della cassa e della banca
- **Nome della funzione:** Modulo di dettaglio della transazione contrassegnato

## <a name="additional-resources"></a>Risorse aggiuntive

- [Residuo liquidazione](settle-remainder.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
