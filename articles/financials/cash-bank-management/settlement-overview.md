---
title: Panoramica della compensazione/liquidazione
description: Questo articolo fornisce informazioni generali sul processo di liquidazione. Descrive i tipi di transazioni che possono essere liquidate, quando, come e i risultati del processo di liquidazione.
author: kweekley
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14551
ms.assetid: 0968fa71-5984-415b-8689-759a0136d5d1
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 2f1f11a7f1340d408374e658ae616ffa99f3c911
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="settlement-overview"></a>Panoramica della compensazione/liquidazione

[!include[banner](../includes/banner.md)]


Questo articolo fornisce informazioni generali sul processo di liquidazione. Descrive i tipi di transazioni che possono essere liquidate, quando, come e i risultati del processo di liquidazione.

Durante la compensazione, le transazioni in un documento vengono applicate alle transazioni in un altro documento per aumentare o diminuire il saldo di ciascun documento. È possibile ad esempio applicare un pagamento a una fattura. È possibile liquidare vari tipi di transazioni, in momenti diversi e con metodi diversi. La compensazione può anche indurre la generazione di nuove transazioni.

## <a name="what-transactions-can-be-settled"></a>Quali transazioni possono essere compensate
La compensazione nella contabilità fornitori e nella contabilità clienti può verificarsi tra tutti i tipi di transazione che interessano il saldo fornitore o il saldo cliente, ad esempio fatture, pagamenti, note di credito e commissioni. Qualsiasi tipo di transazione può essere compensato a fronte di qualsiasi altro tipo di transazione. Ad esempio, è possibile compensare un pagamento a fronte di una fattura, una nota di credito a fronte di una fattura, una fattura a fronte di una fattura e un pagamento a fronte di un pagamento. È possibile compensare pagamenti a fronte di una transazione nella stessa persona giuridica o in una persona giuridica diversa. Nelle organizzazioni che utilizzano un modello di pagamento centralizzato, i [pagamenti centralizzati](set-up-centralized-payments.md) possono semplificare il processo di pagamento.

## <a name="when-to-settle-transactions"></a>Quando compensare transazioni
Le transazioni possono essere compensate al momento della registrazione della voce di pagamento. Ad esempio, quando si effettua un pagamento a un fornitore, in genere si selezionano le fatture da pagare. Selezionando le fatture, le transazioni vengono contrassegnate per la liquidazione a fronte del pagamento. Quando gli addetti ai pagamenti della contabilità clienti registrano un pagamento cliente, è possibile contrassegnare le fatture appropriate per la liquidazione, in base alle informazioni incluse nel pagamento del cliente. La pagina **Liquida transazioni** verrà utilizzata per contrassegnare le transazioni per la liquidazione. Questa pagina può essere aperta da qualsiasi fattura o pagamento non registrato. Quando la transazione viene registrata, anche la liquidazione viene registrata. Le transazioni possono inoltre essere liquidate dopo la registrazione. È possibile immettere e registrare un pagamento cliente senza compensarlo a fronte di alcuna fattura. Tuttavia, potrebbe essere necessario prima eseguire una ricerca, per assicurarsi che il pagamento venga compensato a fronte della fattura corretta. La pagina **Liquida transazioni** può essere aperta dalla pagina **Tutti i clienti** o **Tutti i fornitori** o dalla pagina **Transazioni** per qualsiasi cliente o fornitore. È inoltre possibile prenotare pagamenti anticipati registrati per una fattura contrassegnando il pagamento per la compensazione a fronte di un ordine fornitore o un ordine cliente. In questo caso, il pagamento ha ancora un saldo aperto, ma non può essere liquidato a fronte di un'altra fattura. Il pagamento verrà automaticamente liquidato a fronte della fattura creata dall'ordine fornitore o dall'ordine cliente.

## <a name="how-to-settle-transactions"></a>Come compensare transazioni
Le transazioni possono essere compensate manualmente, automaticamente, o tramite una combinazione dei due metodi. La scelta di un metodo di compensazione dipende dai processi aziendali, che possono quindi essere implementati nell'impostazione della liquidazione nei parametri di contabilità clienti e dei parametri di contabilità fornitori. È possibile creare pagamenti fornitore e i pagamenti in addebito diretto cliente mediante una proposta di pagamento, utilizzata per selezionare le fatture da pagare. La proposta di pagamento viene avviata manualmente, ma Microsoft Dynamics 365 for Finance and Operations contrassegna automaticamente le fatture selezionate per la liquidazione quando vengono creati i pagamenti. Se i pagamenti vengono creati manualmente, è possibile utilizzare la pagina **Liquida transazioni** per selezionare le fatture per la liquidazione. È possibile selezionare manualmente le fatture, oppure utilizzare l'opzione **Contrassegna in base a priorità** per contrassegnare automaticamente le fatture per la liquidazione. L'opzione **Contrassegna in base a priorità** è disponibile solo per la contabilità clienti. Per abilitare questa opzione, utilizzare la pagina **Priorità liquidazione** nei parametri di contabilità clienti. Se un addetto al pagamento immette un pagamento, ma non liquida il pagamento prima di registrarlo, il pagamento può essere liquidato automaticamente. È possibile abilitare la liquidazione automatica nei parametri di contabilità clienti e nei parametri di contabilità fornitori. Quando si utilizza la liquidazione automatica, è possibile utilizzare l'ordine di liquidazione predefinito oppure definire un ordine di priorità di liquidazione nei parametri di contabilità clienti. Questa funzionalità è disponibile solo per la contabilità clienti.

## <a name="results-of-settlement"></a>Risultati della compensazione
Quando le transazioni vengono liquidate, il saldo scoperto di ciascuna transazione viene conseguentemente aumentato o diminuito. In uno scenario tipico, in cui una fattura e un pagamento vengono compensati, lo stato e il saldo di ciascuna transazione vengono aggiornati in base alle seguenti regole:

-   Se l'importo del pagamento è superiore all'importo della fattura, il saldo della fattura viene ridotto a 0,00 e la fattura viene chiusa. Il pagamento rimarrà aperto e il saldo è l'importo del quale il pagamento supera l'importo della fattura.
-   Se l'importo del pagamento è inferiore all'importo della fattura, il saldo del pagamento viene ridotto a 0,00 e il pagamento viene chiuso. La fattura rimarrà aperta e il saldo è l'importo per il quale il pagamento non ha coperto l'importo della fattura.
-   Se l'importo del pagamento è uguale all'importo della fattura, il pagamento e la fattura vengono entrambi chiusi e il saldo di entrambi è 0,00.

Se [il pagamento è inferiore all'importo della fattura](../accounts-payable/vendor-payments-partial-amount.md) a causa di uno sconto di cassa, un annullamento o un pagamento insufficiente, la fattura e il pagamento potrebbero comunque venire chiusi, a seconda dell'impostazione della liquidazione nei parametri di contabilità clienti e nei parametri di contabilità fornitori. La compensazione può anche generare transazioni. Ad esempio, la compensazione di una fattura e di un pagamento può produrre uno sconto di cassa, un profitto o una perdita realizzata, rettifiche di VAT, annullamenti o differenze in centesimi.




