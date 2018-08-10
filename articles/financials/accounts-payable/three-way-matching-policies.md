---
title: Criteri di abbinamento a tre elementi di verifica
description: Questo argomento fornisce esempi di abbinamento a tre elementi di verifica.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendInvoicePostingHistory
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 2761
ms.assetid: 70f3cb1a-18b7-4474-95ec-28b2410dd8f8
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: c8ea45ece05f006f1649c79fcdee427a0bc4b0b5
ms.contentlocale: it-it
ms.lasthandoff: 03/26/2018

---

# <a name="three-way-matching-policies"></a>Criteri di abbinamento a tre elementi di verifica

[!include [banner](../includes/banner.md)]

Questo argomento fornisce esempi di abbinamento a tre elementi di verifica.

<a name="example-three-way-matching-for-items"></a>Esempio: criteri di abbinamento a tre elementi di verifica per gli articoli
-------------------------------------

**Riepilogo:** Ken è il supervisore presso la sede centrale aziendale di una persona giuridica denominata Fabrikam. Ken stabilisce che tutte le fatture fornitore basate su ordini fornitore devono essere abbinate a righe di ordini fornitore (abbinamento a due elementi di verifica). Per gli acquisti di articoli che verranno utilizzati come cespiti, le fatture devono essere abbinate sia alle righe ordine fornitore che alle righe entrata prodotti (abbinamento a tre elementi di verifica).

Fabrikam opera con più persone giuridiche e dipendenti in tutto il mondo. Con l'aumento del volume di transazioni, aumentano anche le discrepanze tra le entrate e le fatture. Ciò determina l'ammortamento dei cespiti. Le fatture dei fornitori vengono pagate, ma il processo non include l'identificazione delle discrepanze quando viene ricevuto un numero inferiore di articoli rispetto all'ordinato o quando gli articoli non vengono ricevuti affatto. Inoltre la spesa aumenta poiché i dipendenti necessitano comunque degli strumenti e di altri materiali per svolgere le proprie mansioni. Ken desidera assicurarsi che i fornitori spediscano i prodotti ordinati e che gli articoli vengano ricevuti dai dipendenti Fabrikam. Di conseguenza, Ken richiede l'applicazione dei criteri di abbinamento a due e a tre elementi di verifica per tutte le persone giuridiche dell'organizzazione. L'abbinamento fatture facilita la traccia e la risoluzione dei problemi relativi ad articoli scomparsi o non ricevuti. 

I criteri di abbinamento fatture in questo esempio sono di supporto alle persone con i ruoli seguenti nel raggiungimento di questi obiettivi:

-   Ken è il supervisore dell'impresa Fabrikam. Può aiutare le persone nella propria organizzazione a identificare e correggere i problemi relativi a ordini, entrate e pagamenti di articoli (beni e servizi) dei fornitori.
-   Phyllis e April sono responsabili della contabilità nel reparto contabilità fornitori della divisione statunitense di Fabrikam. Possono applicare i criteri aziendali e assicurarsi che le fatture vengano pagate solo dopo che sono state abbinate all'ordine fornitore e alle entrate di beni e servizi, ove applicabile.
-   Tony è responsabile di produzione nella divisione statunitense di Fabrikam. Insieme ad altri membri del personale di produzione può assicurarsi che gli articoli vengano ricevuti come sono stati ordinati ai fornitori e siano conteggiati in modo che il personale disponga del necessario per lo svolgimento delle relative mansioni.

### <a name="prerequisites"></a>Prerequisiti

-   Ken imposta i criteri di abbinamento a livello di persona giuridica su Abbinamento a tre elementi di verifica.
-   Ken imposta l'opzione Aggiorna automaticamente lo stato dell'intestazione fattura per la persona giuridica su Sì.
-   Ken imposta il campo Associa prezzi totali per la persona giuridica su percentuale e immette 15% come percentuale di tolleranza.
-   Ken imposta i criteri di abbinamento a livello di articolo per l'articolo 1500 - Computer CNC Milicron su Abbinamento a tre livelli di verifica. Questo articolo è un cespite utilizzato per la produzione in Fabrikam. Le fatture per questo articolo vengono abbinate alle righe ordine fornitore per i prezzi e alle entrate prodotti per le quantità.
-   Tony immette una richiesta di approvvigionamento per cinque computer CNC Milicron. Alicia, un'addetta agli ordini fornitore in Fabrikam, emette un ordine fornitore a una persona giuridica denominata Contoso per la fornitura degli articoli.

    | Numero articolo                 | Quantità | Prezzo unitario | Importo netto | Codice spese        | Valore spese |
    |-----------------------------|----------|------------|------------|---------------------|---------------|
    | 1500 - Computer CNC Milicron | 5        | 8.000,00   | 40.000,00  | Spedizione | 3.000,00      |

-   Arnie, un addetto della contabilità clienti in Contoso, verifica le spedizioni per la settimana. Seleziona le transazioni di spedizione da fatturare a Fabrikam per la consegna dei computer CNC Milicron e include un addebito per la spedizione. Fabrikam considererà l'addebito come parte del costo del cespite.

### <a name="scenario"></a>Scenario

1.  Sammy, un lavoratore nel reparto addetto al ricevimento in Fabrikam, riceve la quantità totale di computer forniti da Contoso. Immette una quantità di 5 in un'entrata prodotti. Poiché l'ordine fornitore è stato interamente ricevuto, lo stato dell'ordine fornitore cambia in Ricevuto.
2.  April, che coordina la contabilità fornitori in Fabrikam, immette e verifica la fattura che viene inviata da Contoso. Verifica le informazioni seguenti:
    -   Per gli articoli che richiedono i criteri di abbinamento a tre elementi di verifica, la quantità nella riga fattura corrisponde alla quantità ricevuta. La quantità ricevuta è indicata nell'entrata prodotti abbinata alla fattura.
    -   Per gli articoli che richiedono i criteri di abbinamento a due o a tre elementi di verifica, i prezzi nella riga fattura rientrano nelle tolleranze definite in Microsoft Dynamics 365 for Finance and Operations. Sono inclusi i seguenti tipi di abbinamento prezzi:
        -   Abbinamento dei prezzi unitari netti: il prezzo unitario netto nella riga fattura corrisponde al prezzo unitario netto nella riga ordine fornitore nella percentuale di tolleranza. In questo esempio la tolleranza del prezzo unitario netto è pari a +8%.
        -   Abbinamento totali dei prezzi: l'importo netto della riga fattura corrisponde all'importo netto della riga ordine fornitore in termini di percentuale o importo di tolleranza o entrambi. In questo esempio la tolleranza di abbinamento dei totali dei prezzi è pari a +15%.

La fattura su carta di Contoso contiene le informazioni seguenti.

| Articolo                        | Quantità | Prezzo unitario | Importo netto |
|-----------------------------|----------|------------|------------|
| 1500 - Computer CNC Milicron | 5        | 8.100,00   | 40.500,00  |
| Spedizione e gestione       |          |            | 4.000,00   |
| Imposta sul reddito                         |          |            | 0,00       |
| Totale                       |          |            | 44.500,00  |

In Finance and Operations la riga fattura include le seguenti informazioni.

| Numero articolo                 | Quantità | Prezzo unitario | Importo netto riga | Criteri di abbinamento    | Abbinamento quantità entrata prodotti | Abbinamento prezzi | Abbinamento totale prezzo |
|-----------------------------|----------|------------|-----------------|--------------------|--------------------------------|-------------|-------------------|
| 1500 - Computer CNC Milicron | 5        | 8.100,00   | 40.500,00       | Criteri di abbinamento a tre elementi di verifica | Superata                         | Superata      | Superata            |

Poiché la riga supera la prova del processo di abbinamento fatture, la fattura può essere registrata.

## <a name="example-three-way-matching-for-item-and-vendor-combinations"></a>Esempio: criteri di abbinamento a tre elementi di verifica per combinazioni di fornitore e articolo
Riepilogo: Ken è il supervisore presso la sede centrale aziendale di una persona giuridica denominata Fabrikam. Ken stabilisce che tutte le fatture basate su ordini fornitore devono essere abbinate a righe ordine fornitore (abbinamento a due elementi di verifica). Cassie si occupa della contabilità nella divisione di Fabrikam in Malaysia. Specifica che gli articoli selezionati ordinati presso determinati fornitori in Malaysia devono essere abbinati sia alle righe ordine fornitore che alle righe entrata prodotti (criteri di abbinamento a tre elementi di verifica). Può inoltre sostituire i criteri di abbinamento con un livello più alto di abbinamento per ordini fornitore specifici. 

Il volume e gli importi sono di piccola entità e si sono verificati dei problemi di consegna da parte di alcuni fornitori in Malaysia. Per questi motivi, Cassie imposta il livello di controllo per determinate combinazioni di fornitore e articolo che vengono ottenute in Malaysia sui criteri di abbinamento a tre elementi di verifica. 

I criteri di abbinamento fatture in questo esempio sono di supporto alle persone con i ruoli seguenti nel raggiungimento di questi obiettivi:
-   Ken è il supervisore dell'impresa Fabrikam. Può aiutare le persone nella propria organizzazione a identificare e correggere i problemi relativi a ordini, entrate e pagamenti di articoli (beni e servizi) dei fornitori.
-   Cassie si occupa della contabilità nella divisione di Fabrikam in Malaysia. Può applicare i criteri aziendali e assicurarsi che le fatture vengano pagate solo dopo che sono state abbinate alle righe ordine fornitore e alle entrate prodotti che rappresentano il ricevimento di beni e servizi. Inoltre, aumenta il livello di controllo dei criteri di abbinamento a tre elementi di verifica per articoli specifici allo scopo di tenere sotto controllo i costi operativi.

### <a name="prerequisites"></a>Prerequisiti

-   Ken imposta i criteri di abbinamento a livello di persona giuridica su Abbinamento a due elementi di verifica.
-   Ken imposta il campo Associa prezzi totali per la persona giuridica su percentuale e immette 10% come percentuale di tolleranza.
-   Ken imposta la tolleranza del prezzo unitario di tutti gli articoli su 2%.
-   Cassie imposta i criteri di abbinamento a livello di combinazione di fornitore e articolo per l'articolo PH2500 - Computer e fornitore Contoso su Abbinamento a tre livelli di verifica.
-   Alicia, un'addetta agli ordini fornitore nella divisione di Fabrikam in Malaysia, emette gli ordini fornitore a Contoso per la fornitura di tre articoli, come illustrato nella seguente tabella. Quando crea l'ordine fornitore, sostituisce i criteri di abbinamento per il mouse wireless impostandoli sull'abbinamento a tre elementi di verifica anziché a due elementi.

    | Numero articolo           | Quantità | Prezzo unitario | Importo netto | Criteri di abbinamento (valore predefinito) | Criteri di abbinamento (nella riga ordine fornitore) |
    |-----------------------|----------|------------|------------|---------------------------------|----------------------------------------------|
    | PH2500 - Computer     | 2        | 2.500,00   | 5.000,00   | Criteri di abbinamento a tre elementi di verifica              | Criteri di abbinamento a tre elementi di verifica                           |
    | MM01 - Mouse wireless | 2        | 40,00      | 80,00      | Criteri di abbinamento a due elementi di verifica                | Criteri di abbinamento a tre elementi di verifica                           |
    | Unità USB             | 200      | 10,00      | 2.000,00   | Criteri di abbinamento a due elementi di verifica                | Criteri di abbinamento a due elementi di verifica                             |

### <a name="scenario"></a>Scenario

1.  Gli articoli arrivano. Sammy, un lavoratore nel reparto addetto al ricevimento della divisione di Fabrikam in Malaysia, viene interrotto e non registra l'entrata prodotti immediatamente.
2.  April, che coordina la contabilità fornitori in Fabrikam, immette e verifica la fattura che viene inviata da Contoso. Verifica le informazioni seguenti:
    -   Per gli articoli che richiedono i criteri di abbinamento a tre elementi di verifica, la quantità nella riga fattura corrisponde alla quantità ricevuta. La quantità ricevuta è indicata nell'entrata prodotti abbinata alla fattura.
    -   Per gli articoli che richiedono i criteri di abbinamento a due o a tre elementi di verifica, i prezzi nella riga fattura rientrano nelle tolleranze definite in Finance and Operations. Sono inclusi i seguenti tipi di abbinamento prezzi:
        -   Abbinamento dei prezzi unitari netti: il prezzo unitario netto nella riga fattura corrisponde al prezzo unitario netto nella riga ordine fornitore nella percentuale di tolleranza. In questo esempio la tolleranza del prezzo unitario netto è pari a +2%.
        -   Abbinamento totali dei prezzi: l'importo netto della riga fattura corrisponde all'importo netto della riga ordine fornitore in termini di percentuale o importo di tolleranza o entrambi. In questo esempio la tolleranza di abbinamento dei totali dei prezzi è pari a +10%.

La fattura su carta di Contoso contiene le informazioni seguenti.

| Articolo                  | Quantità | Prezzo unitario | Importo netto |
|-----------------------|----------|------------|------------|
| PH2500 - Computer     | 2        | 2.500,00   | 5.000,00   |
| MM01 - Mouse wireless | 2        | 41,00      | 82,00      |
| Unità USB             | 200      | 10,05      | 2.010,00   |
| Fattura totale         |          |            | 7.092,00   |

In Finance and Operations la riga fattura include le seguenti informazioni.

| Numero articolo           | Quantità | Prezzo unitario | Importo netto riga | Criteri di abbinamento    | Abbinamento quantità entrata prodotti | Abbinamento prezzi | Abbinamento totale prezzo |
|-----------------------|----------|------------|-----------------|--------------------|--------------------------------|-------------|-------------------|
| PH2500 - Computer     | 2        | 2.500,00   | 5.000,00        | Criteri di abbinamento a tre elementi di verifica | Non riuscita                         | Superata      | Superata            |
| MM01 - Mouse wireless | 2        | 41,00      | 82,00           | Criteri di abbinamento a tre elementi di verifica | Non riuscita                         | Non riuscita      | Superata            |
| Unità USB             | 200      | 10,05      | 2010,00         | Criteri di abbinamento a due elementi di verifica   |                                | Superata      | Superata            |

Notare gli articoli seguenti:
-   Per la riga PH2500 - Computer, la colonna Abbinamento quantità entrata prodotti include un'icona di avviso poiché la riga fattura non è abbinata a un'entrata prodotti.
-   Per la riga MM01 - Mouse wireless, la colonna Abbinamento quantità entrata prodotti include un'icona di avviso poiché la riga fattura non è abbinata a un'entrata prodotti. La colonna Abbinamento prezzi unitari include un'icona di avviso poiché la tolleranza del 2% stabilita per il prezzo unitario netto è stata superata.
-   Per la riga Unità USB, la colonna Abbinamento quantità entrata prodotti è vuota poiché l'abbinamento a due elementi di verifica non corrisponde alle quantità della riga fattura e della riga entrata prodotti.

Se è necessaria l'approvazione per la registrazione delle fatture in presenza di discrepanze di abbinamento fatture, la casella di controllo Approva registrazione con discrepanze di abbinamento nella pagina Dettagli abbinamento fatture deve essere selezionata prima che la fattura possa essere registrata con errori di abbinamento prezzi ed errori di abbinamento quantità. Se l'approvazione non è richiesta, l'elaborazione della fattura può continuare se non sono presenti altri errori di registrazione.


Per ulteriori informazioni, vedere [Abbinamento fatture della contabilità fornitori](accounts-payable-invoice-matching.md).




