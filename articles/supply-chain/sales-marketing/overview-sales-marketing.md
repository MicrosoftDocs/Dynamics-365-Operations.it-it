---
title: Panoramica di Vendite e marketing
description: È possibile utilizzare Vendite e marketing per ottenere, archiviare e utilizzare vari tipi di dati nel flusso di vendita. Ciò include l'iniziativa di vendita iniziale, azioni follow-up successive e vendite aggiuntive.
author: kfend
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 92303
ms.assetid: 65ca9992-bbfa-4224-bf0e-067a25c7e6a4
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7b079e560f006c7dc9df1cb6e4642f6bff0e1417
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5218419"
---
# <a name="sales-and-marketing-overview"></a>Panoramica di Vendite e marketing

[!include [banner](../includes/banner.md)]

È possibile utilizzare Vendite e marketing per ottenere, archiviare e utilizzare vari tipi di dati nel flusso di vendita. Ciò include l'iniziativa di vendita iniziale, azioni follow-up successive e vendite aggiuntive.

<a name="marketing"></a>Marketing
---------

Utilizzare campagne e attività di marketing per individuare e sviluppare relazioni con potenziali clienti, in modo che le interazioni iniziali possono trasformarsi in relazioni di vendita. Nel flusso di processo riportato di seguito è illustrato il processo aziendale per il marketing. [![Processo aziendale per il marketing](./media/marketing01.jpg)](./media/marketing01.jpg)

### <a name="relationships"></a>Relazioni

In vendite e marketing, le interazioni iniziali con potenziali clienti possono verificarsi in diverse situazioni. È possibile, ad esempio, trovare un potenziale cliente mentre si partecipa a una fiera o si potrebbe avere un possibile lead con un cliente dopo l'esecuzione di una campagna di mailing di massa da parte dell'organizzazione. È molto importante comprendere il flusso dell'entità di una parte prima che diventi un cliente. Nell'immagine seguente è illustrato il flusso di relazioni di entità quando un potenziale cliente diventa un cliente effettivo. [![SalesandMarketing01](./media/salesandmarketing01.jpg)](./media/salesandmarketing01.jpg)

### <a name="campaigns"></a>Campagne

Una campagna è destinata ai contatti per i prospect, i clienti potenziali, le opportunità e i clienti selezionati per partecipare alla campagna. In Supply Chain Management, è possibile creare diversi tipi di campagne, quali telemarketing, mailing e campagne di posta elettronica, per massimizzare il potenziale di clienti. Man mano che avanza la campagna e si ricevono risposte positive, è possibile iniziare il processo di vendita con i destinatari che hanno risposto positivamente alla campagna.

## <a name="sales"></a>Vendite
Utilizzare la funzionalità di vendita per creare le offerte, effettuare l'upselling e il cross-selling a clienti nuovi ed esistenti, creare ordini cliente e creare fatture di vendita per i clienti. Nel flusso di processo riportato di seguito è illustrato il processo aziendale per le vendite. [![Processo aziendale per le vendite](./media/sales01.jpg)](./media/sales01.jpg)

### <a name="sales-quotations"></a>Offerte di vendita

Creare offerte di vendita per presentare ai clienti un'offerta di beni o servizi. Un cliente potrebbe richiedere un'offerta oppure è possibile creare un'offerta in risposta a una richiesta da un cliente potenziale o esistente. Quando il cliente approva l'offerta di vendita, è possibile convertirla in un ordine cliente.

### <a name="up-sellcross-sell"></a>Up-selling/cross-selling

Upselling e cross-sell sono le tecniche per la vendita di prodotti quando si immette un ordine per un cliente. In upselling, viene suggerito un altro prodotto anziché il prodotto corrente. In cross-selling, viene suggerito un prodotto in aggiunta al prodotto corrente. Quando si impostano gli elenchi di prodotti, è possibile creare regole specifiche per indicare quando deve essere suggerito un prodotto come prodotto di upselling o cross-selling.

### <a name="sales-orders"></a>Ordini cliente

Quando si crea un nuovo ordine cliente, è necessario selezionare il tipo da creare. Sono disponibili cinque opzioni. **Nota:** dopo aver creato un ordine cliente, qualsiasi tipo di ordine può essere modificato fatta eccezione per il tipo **Richieste articoli** se lo stato dell'ordine cliente è **Consegnato**.

| Tipo di ordine cliente  | Descrizione                                                                                                                                                                                                                                                                                            |
|-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Giornale di registrazione           | Utilizzare questo tipo come bozza per un ordine cliente. Questo tipo non ha alcun effetto sulle quantità in magazzino e non genera transazioni articolo.                                                                                                                                                                    |
| Sottoscrizione      | Utilizzare questo tipo per gli ordini ricorrenti. Quando l'ordine viene fatturato, il relativo stato viene impostato automaticamente su ordine aperto. La quantità consegnata viene fatturata e le consegne rimanenti vengono aggiornate. Non è possibile utilizzare questo tipo di ordine cliente se si utilizza la funzionalità Gestione magazzino. |
| Ordine cliente       | Utilizzare questo tipo quando un cliente ha effettuato o confermato un ordine .                                                                                                                                                                                                                                        |
| Ordine di reso    | Utilizzare questo tipo quando un cliente restituisce un articolo. Viene assegnato automaticamente un numero di reso articolo (NAR).                                                                                                                                                                                            |
| Richieste articoli | Questo tipo viene creato automaticamente quando si effettua la vendita di un articolo tramite un progetto.                                                                                                                                                                                                                       |

### <a name="sales-agreements"></a>Contratti di vendita

Un contratto di vendita è un contratto con cui il cliente si impegna ad acquistare un prodotto in una determinata quantità o per uno specifico importo nel tempo in cambio di sconti o prezzi speciali. I prezzi e gli sconti del contratto di vendita prevalgono su tutti i prezzi e gli sconti dichiarati in eventuali contratti commerciali esistenti. Un contratto di vendita è valido per periodo definito. La data di spedizione richiesta specificata per una vendita nella pagina **Ordine cliente** deve essere compresa nel periodo di validità. Per impostazione predefinita, un contratto di vendita è in attesa. È possibile effettuare un ordine da un contratto di vendita solo se tale contratto è impostato su **Valido**.

### <a name="backorders"></a>Ordini arretrati

Durante l'immissione e la convalida degli ordini, può essere necessario gestire ordini arretrati ed eccezioni prima di poter portare a termine la vendita. Gli ordini arretrati sono ordini fornitore non ancora consegnati da un fornitore o ordini cliente non ancora consegnati a un cliente. Il follow-up degli ordini arretrati è un'attività importante. Ad esempio, se la consegna dei prodotti viene ritardata da un fornitore, potrebbe essere necessario modificare la data di consegna a un cliente e informare quest'ultimo del ritardo. È possibile visualizzare gli ordini arretrati per articolo, cliente o fornitore.

#### <a name="viewing-backorders-by-item"></a>Visualizzare gli ordini arretrati per articolo

La visualizzazione degli ordini arretrati per articolo consente di svolgere l'attività di follow-up sulla base del futuro flusso di transazioni previsto relativamente a un articolo specifico. È ad esempio possibile controllare le informazioni seguenti .

-   Il numero di ordini cliente emessi per un articolo
-   Se sono ancora mancanti consegne dell'articolo dai fornitori
-   Se dovranno essere ordinati più articoli per poter rispettare la consegna di tutti gli ordini cliente alla scadenza.

Eseguendo questo controllo, è possibile rispondere alle richieste dai clienti sui tempi di consegna dell'articolo. È inoltre possibile assegnare priorità agli ordini cliente arretrati e dividere gli articoli disponibili tra gli ordini.

#### <a name="viewing-backorders-by-customer"></a>Visualizzare gli ordini arretrati per cliente

La visualizzazione degli ordini arretrati per cliente consente di visualizzare lo stato degli ordini rimanenti del cliente. Questo controllo è utile quando è necessario rispondere ai clienti in attesa degli articoli che sono in ritardo.

#### <a name="viewing-backorders-by-vendor"></a>Visualizzare gli ordini arretrati per fornitore

Quando si visualizzano gli ordini arretrati per fornitore, è possibile controllare le consegne mancanti e le date di consegna previste. Questo controllo è inoltre utile per l'assegnazione di priorità agli ordini arretrati quando i prodotti arrivano dai fornitori ed è necessario selezionare gli ordini cliente per la consegna.

### <a name="invoices"></a>Fatture

Durante il processo di vendita, è possibile creare tre tipi di fatture:

-   Fattura cliente
-   Fattura a testo libero
-   Fattura proforma

#### <a name="customer-invoice"></a>Fattura cliente

Una fattura cliente è un conto che un'organizzazione presenta a un cliente in relazione a una vendita. Questo tipo di fattura cliente viene creato in base a un ordine cliente che include un'intestazione e una o più righe per articoli o servizi. La fattura cliente completa il ciclo ordine cliente, documento di trasporto e fattura di vendita.  

È possibile registrare e stampare una fattura cliente unica, basata su un ordine cliente o sul documento di trasporto e la data. È anche possibile registrare e stampare più fatture cliente insieme, in base ai documenti di trasporto e alle date. Quando viene registrata una singola fattura cliente usando l'ordine cliente, la quantità **Rimanente fattura** relativa a ciascun articolo viene aggiornata con il totale delle quantità fatturate, tratto dall'ordine cliente selezionato.  

Se entrambe le quantità **Rimanente fattura** e **Rimanente consegna** per tutti gli articoli dell'ordine cliente sono uguali a 0 (zero), lo stato dell'ordine cliente passa a **Fatturato**. Se la quantità di uno dei due campi è diversa da zero, lo stato dell'ordine cliente non viene modificato ed è possibile immettere ulteriori fatture. Se si prevede di registrare e stampare una o più fatture cliente basate sui documenti di trasporto, è necessario avere già registrato almeno un documento di trasporto per ogni ordine cliente. La fattura cliente si basa sui documenti di trasporto e riflette le quantità elencate.  

È possibile creare una fattura cliente in base agli articoli delle righe dei documenti di trasporto spediti fino alla data corrente, anche se non sono stati ancora spediti tutti gli articoli di un ordine cliente specifico. Questa funzionalità è utilizzabile, ad esempio, se per ogni cliente la persona giuridica emette una fattura al mese per coprire tutte le consegne del mese in questione. Ogni documento di trasporto corrisponde a una consegna completa o parziale dell'ordine cliente.  

Quando la fattura viene registrata, la quantità **Rimanente fattura** per ogni articolo viene aggiornata con il totale delle quantità consegnate, tratto dai documenti di trasporto selezionati. Se le quantità **Rimanente fattura** e **Rimanente consegna** per tutti gli articoli dell'ordine cliente sono uguali a 0 (zero), lo stato dell'ordine cliente passa a **Fatturato**. Se la quantità è diversa da zero, lo stato dell'ordine cliente non viene modificato ed è possibile immettere ulteriori fatture. Le transazioni di magazzino vengono aggiornate con il numero di fattura e lo stato nella riga dell'ordine cliente passa a **Fatturato**.

#### <a name="free-text-invoice"></a>Fattura a testo libero

Una fattura a testo libero è una fattura non correlata a un ordine cliente. Contiene righe ordine che includono conti CoGe, descrizioni a testo libero e un importo di vendita. Non è possibile immettere un numero di articolo su questo tipo di fattura, ed è necessario immettere le informazioni appropriate sull'IVA. È indicato un conto principale per la vendita in ogni riga di fattura. Il saldo cliente viene registrato nel conto riepilogativo dal profilo di registrazione utilizzato per la fattura a testo libero.

#### <a name="pro-forma-invoice"></a>Fattura proforma

Una fattura proforma è una fattura preparata come stima degli importi effettivi prima della registrazione della fattura vera e propria. È possibile stampare una fattura di questo tipo per una fattura cliente o per una fattura a testo libero.

### <a name="additional-resources"></a>Risorse aggiuntive

#### <a name="blogs"></a>Blog

È possibile trovare una panoramica del processo di vendita nel post [Processo di vendita in Dynamics 365 for Finance and Operations](https://financefunction.tech/2018/05/15/how-sales-work-in-dynamics-365-for-finance-and-operations).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]