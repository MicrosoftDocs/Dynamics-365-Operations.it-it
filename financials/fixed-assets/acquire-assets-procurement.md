---
title: Acquisire cespiti tramite approvvigionamento
description: "Questo articolo descrive come impostare l&quot;integrazione di Cespiti con la contabilità fornitori in modo da consentire la creazione automatica di cespiti a partire da ordini o fatture fornitore oppure la registrazione automatica di transazioni di acquisizione e di rettifica acquisizione per i cespiti."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetParameters
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3481
ms.assetid: d4e73a3f-633b-48b2-b8db-7a4a59a4d7ec
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3b16ef53f9fb57a6663db0be1f7e0a57471db2fb
ms.openlocfilehash: 8f3fb9889a0870021a9799b8a3c78237b9bc9731
ms.lasthandoff: 03/31/2017


---

# <a name="acquire-assets-through-procurement"></a>Acquisire cespiti tramite approvvigionamento

Questo articolo descrive come impostare l'integrazione di Cespiti con la contabilità fornitori in modo da consentire la creazione automatica di cespiti a partire da ordini o fatture fornitore oppure la registrazione automatica di transazioni di acquisizione e di rettifica acquisizione per i cespiti.

 Sono disponibili i seguenti metodi per l'integrazione di Cespiti e Contabilità fornitori. È necessario utilizzare lo stesso metodo per tutti i cespiti.
-   Viene creato manualmente un cespite prima di aggiungere il numero cespite alla riga della fattura o dell'ordine fornitore. Quando si registra la fattura fornitore, viene registrata automaticamente una transazione di acquisizione per il cespite. Questo è il metodo predefinito.
-   Viene creato manualmente un cespite prima di aggiungere il numero cespite alla riga della fattura o dell'ordine fornitore. Quando si registra la fattura fornitore, non viene registrata alcuna transazione di acquisizione per il cespite.
-   Viene creato automaticamente un cespite quando si registra un'entrata prodotti o una fattura fornitore per il quale è selezionata la casella di controllo Crea un nuovo cespite. Quando si registra la fattura fornitore, viene registrata automaticamente una transazione di acquisizione per il cespite.
-   Viene creato automaticamente un cespite quando si registra un'entrata prodotti o una fattura fornitore per il quale è selezionata la casella di controllo Crea un nuovo cespite. Quando si registra la fattura fornitore, non viene registrata alcuna transazione di acquisizione per il cespite.

Selezionare uno dei primi due metodi se si preferisce creare manualmente i cespiti e assegnarne il numero alla fattura o all'ordine fornitore. Selezionare invece uno degli ultimi due metodi se si preferisce un approccio più flessibile, in modo che sia possibile a volte creare manualmente i cespiti e a volte creare automaticamente un cespite in base alle informazioni rilevanti contenute nei dettagli della voce. 

Indipendentemente dal fatto che i cespiti vengano creati manualmente o che venga adottato un approccio più flessibile, è inoltre necessario decidere se una transazione di acquisizione può essere registrata solo in Cespiti oppure contestualmente alla registrazione di una fattura fornitore. In alcune organizzazioni si preferisce che gli utenti creino manualmente le transazioni di acquisizione e di rettifica acquisizione in Cespiti mediante l'inserimento manuale nei giornali di registrazione o l'utilizzo di proposte. 

In questo argomento vengono forniti i dettagli relativi a ciascun metodo.

## <a name="methods-for-manually-creating-fixed-assets"></a>Metodi per la creazione manuale dei cespiti
Quando si registra una fattura fornitore nelle cui righe è riportato un numero cespite, se nella pagina Parametri cespiti è selezionata la casella di controllo Consenti acquisizione cespiti da Acquisto, l'acquisizione verrà registrata automaticamente e lo stato del cespite verrà impostato su Aperto. 

Se non si riesce a registrare un'acquisizione, è possibile immettere manualmente una transazione di acquisizione in Cespiti oppure utilizzare una proposta di acquisizione nel giornale di registrazione dei cespiti per creare più transazioni di acquisizione contemporaneamente.

> [!NOTE]                                                                                                                              
> Se l'area Cespiti è impostata in modo da limitare la registrazione delle transazioni di acquisizione a un gruppo utenti specifico, sarà necessario essere membri di tale gruppo per registrare le transazioni dalle fatture.

## <a name="methods-for-automatically-creating-fixed-assets"></a> Metodi per la creazione automatica dei cespiti
Quando si registra un'entrata prodotti con la casella di controllo Crea un nuovo cespite selezionata per una riga, viene creato un nuovo cespite con stato Non ancora acquistato. Quando si registra una fattura fornitore con un nuovo cespite, per quest'ultimo viene registrata una transazione di acquisizione e lo stato viene impostato su Aperto, se l'area Cespiti generale è impostata in modo da consentire le acquisizioni di cespiti dalla contabilità fornitori e si è membri di un gruppo utenti in grado di registrare le transazioni di questo tipo. 

Se la casella di controllo Nuovo cespite? non era selezionata nella riga di acquisto al momento dell'entrata prodotti, ma lo era durante la registrazione della fattura fornitore, il nuovo cespite verrà creato e acquisito con stato Aperto, se l'area Cespiti è impostata in modo da consentire la creazione e l'acquisizione. Non verrà creato alcun cespite aggiuntivo quando si registra una fattura fornitore se ne è già stato creato uno durante la registrazione dell'entrata prodotti.

### <a name="capitalization-threshold"></a>Soglia di capitalizzazione

Quando si utilizza un metodo che consente di creare e acquisire automaticamente il cespite, è possibile impostare il sistema in modo da verificare il relativo importo di acquisto rispetto a una determinata soglia di capitalizzazione per l'ammortamento cespiti. In tal caso, l'opzione Ammortamento sarà selezionata nei libri per il cespite quando viene creato dalla contabilità fornitori. 

La soglia di capitalizzazione è l'importo in valuta in base al quale si determina se i cespiti vengono ammortizzati. Se ad esempio si acquista un cespite il cui importo di acquisto è inferiore alla soglia di capitalizzazione, il cespite non verrà ammortizzato. Se invece l'importo di acquisto corrisponde o supera tale soglia, il cespite verrà ammortizzato. 

È possibile impostare la soglia di capitalizzazione nella pagina Gruppi cespite.

## <a name="scenario"></a>Scenario
Nello scenario che segue viene riportato un ciclo completo di un'integrazione di Cespiti con la contabilità fornitori. Viene illustrata una configurazione di esempio e viene inoltre descritto l'utilizzo di proposte di acquisizione. 

In questo scenario il sistema è configurato nel seguente modo:

-   I cespiti vengono creati automaticamente durante la registrazione dell'entrata prodotti o della fattura fornitore, ma l'area Cespiti è impostata in modo da impedire la registrazione delle transazioni di acquisizione dalla contabilità fornitori.
-   I conti vengono specificati nel campo del tipo di conto per i tipi di conto Entrata cespite e Uscita cespite nella pagina Gruppi di articoli.
-   La soglia di capitalizzazione per il gruppo computer (COMP) è 1.500.
-   L'attività dell'utente è quella di immettere un ordine fornitore per un nuovo computer portatile che verrà utilizzato da un dipendente, registrare l'ordine, verificare che l'addetto alle spedizioni registri un'entrata prodotti, registrare la fattura fornitore e controllare che il contabile aggiorni lo stato del cespite computer portatile impostandolo su Aperto.

Per iniziare, è necessario utilizzare la pagina Ordine fornitore per immettere i dettagli relativi al computer portatile, che ha un costo di 1.600. Selezionare l'opzione Nuovo cespite? nella scheda dettaglio Cespiti delle righe dell'ordine fornitore, selezionare COMP come gruppo cespite, quindi salvare l'ordine fornitore. 

Quando arriva il computer portatile, un addetto alle spedizioni immette e registra un'entrata prodotti per registrare l'entrata del computer. Viene creato il relativo cespite con stato Non ancora acquistato. Poiché l'importo supera la soglia di capitalizzazione, viene selezionata l'opzione Ammortamento nei libri per il cespite. Hanno avuto luogo le seguenti transazioni:

| Descrizione                               | Conto             | Dare    | Avere   |
|-------------------------------------------|---------------------|----------|----------|
| Acquisti, acquisti entrata prodotti        | Entrate non fatturate | 1.600,00 |          |
| Acquisti, contropartita acquisti entrata prodotti | Acquisti accumulati   |          | 1.600,00 |

A questo punto, è necessario registrare la fattura fornitore relativa al computer portatile. Lo stato rimane invariato perché il modulo Cespiti è impostato in modo da impedire la registrazione di una transazione di acquisizione cespite quando viene registrata una fattura fornitore. L'opzione Crea un nuovo cespite era selezionata quando la fattura fornitore è stata registrata. Di conseguenza, è stato utilizzato il conto Entrata cespite. Non è stato utilizzato il conto Uscita cespite perché non è stata registrata alcuna acquisizione. Verrà utilizzato in seguito quando il contabile dell'organizzazione registrerà una transazione di acquisizione in Cespiti mediante le proposte di acquisizione. 

Hanno avuto luogo le seguenti transazioni:

| Descrizione                               | Conto             | Dare    | Avere   |
|-------------------------------------------|---------------------|----------|----------|
| Acquisti, contropartita acquisti entrata prodotti | Acquisti accumulati   | 1.600,00 |          |
| Saldo fornitore                            | Contabilità fornitori    |          | 1.600,00 |
| Acquisti, entrata cespite             | Spesa computer    | 1.600,00 |          |
| Acquisti, acquisti entrata prodotti        | Entrate non fatturate |          | 1.600,00 |

Il contabile infine esamina tutti i cespiti con stato Non ancora acquistato, incluso il nuovo cespite computer portatile. Il contabile quindi apre la pagina Proposta di acquisizione dalle righe del giornale di registrazione cespiti e crea transazioni di acquisizione per tutti i cespiti a cui è associata una fattura, ma il cui stato è tuttora impostato su Non ancora acquistato. Quando il giornale di registrazione viene registrato, lo stato del cespite computer portatile passa ad Aperto. Viene effettuato un accredito sul conto Uscita cespite e un addebito sul conto di acquisizione cespiti. 

Per questo scenario sono possibili le seguenti varianti:

-   Se il modulo Cespiti è impostato in modo da consentire la registrazione delle transazioni di acquisizione cespiti durante la registrazione delle fatture fornitore, il contabile non dovrà utilizzare le proposte di acquisizione in Cespiti perché verrà creata la transazione di acquisizione. Quando verrà registrata la fattura fornitore, verranno anche aggiornati diversi conti. Anziché sul conto Spesa computer, viene effettuato un addebito sul conto di magazzino Entrata cespite e hanno luogo due transazioni aggiuntive: viene effettuato un addebito sul conto di acquisizione cespiti e viene effettuato un accredito sul conto di magazzino.
-   Se la casella di controllo Crea un nuovo cespite non è selezionata quando si registra l'entrata prodotti, non verrà creato alcun cespite. Se si seleziona la casella di controllo Crea un nuovo cespite prima di registrare la fattura fornitore, il cespite verrà creato con stato Non ancora acquistato o Aperto se durante la registrazione delle fatture fornitore si registrano anche le transazioni di acquisizione.
-   Se il costo del computer portatile è 1.400 anziché 1.600, la soglia di capitalizzazione non viene raggiunta, pertanto verrà creato il cespite e verrà deselezionata l'opzione Ammortamento.
-   Se è in uso un registro fatture, sarà necessario utilizzare la pagina Giornale di approvazione fatture dopo la registrazione di tale registro per recuperare il giustificativo, collegare l'ordine fornitore alla relativa fattura, selezionare l'opzione Crea un nuovo cespite e registrare la fattura fornitore. Se si è membri di un gruppo utenti in grado di creare transazioni di acquisizione, l'acquisizione verrà creata e lo stato del cespite sarà Aperto.
-   Se viene ricevuta solo una quantità parziale, non verrà creata alcuna acquisizione cespiti per la prima fattura fornitore a causa delle restrizioni relative al gruppo utenti. Sarà possibile registrare un'acquisizione per la seconda fattura fornitore che completa la quantità ordinata solo nel caso in cui sia già stata immessa una transazione di acquisizione per la prima fattura fornitore e si appartenga al gruppo utenti autorizzato a registrare le acquisizioni.


Per ulteriori informazioni, vedere [] integrazione cespiti (fixed-asset-integration.md).


