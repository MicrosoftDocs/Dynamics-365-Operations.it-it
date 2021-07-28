---
title: Creare resi in POS
description: Questo argomento descrive come inizializzare resi per transazioni cash-and-carry o ordini cliente nell'applicazione POS di Microsoft Dynamics 365 Commerce.
author: hhainesms
ms.date: 06/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2020-02-20
ms.dyn365.ops.version: Release 10.0.20
ms.openlocfilehash: c7be9e2d32384df23a4609d82216804fc945061a
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2021
ms.locfileid: "6345186"
---
# <a name="create-returns-in-pos"></a>Creare resi in POS

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Questo argomento descrive come inizializzare resi per transazioni cash-and-carry o ordini cliente nell'app POS di Microsoft Dynamics 365 Commerce.

> [!NOTE]
> Nella versione di Commerce 10.0.20 e successive, è disponibile una nuova funzionalità denominata **Esperienza di elaborazione dei resi unificata in POS**. Questa funzione fornisce un processo di reso più coerente e unificato in POS, indipendentemente dal tipo di transazione (transazione cash-and-carry o ordine cliente) o dal canale originale in cui è stato creato l'ordine. Consigliamo a tutte le organizzazioni di attivare questa nuova funzionalità per migliorare l'affidabilità complessiva dell'elaborazione dei resi tramite POS.
>
> Una volta attivata, la funzione non può essere disattivata.

## <a name="process-returns-by-using-the-return-transaction-operation"></a>Elaborare i resi utilizzando l'operazione di transazione di reso

Consigliamo di aggiungere l'operazione di transazione di reso al POS [layout dello schermo](pos-screen-layouts.md). Nelle versioni precedenti alla versione di Commerce 10.0.20, l'operazione di transazione di reso supporta correttamente l'elaborazione dei resi solo per le transazioni cash-and-carry. Dopo aver attivato la funzione **Esperienza di elaborazione dei resi unificata in POS** in Commerce versione 10.0.20 o successiva, l'operazione di transazione di reso supporta anche l'elaborazione dei resi provenienti dagli ordini cliente, quali gli ordini con prelievo o consegna a domicilio già fatturati.

Dall'operazione di transazione di reso, gli utenti possono cercare una transazione cash-and-carry o un ordine cliente da restituire immettendo uno dei seguenti quattro criteri di ricerca. Gli utenti possono immettere questi criteri utilizzando una tastiera del dispositivo, un tastierino su schermo o uno scanner di codici a barre.

- ID ricevuta
- Numero ordine
- ID di riferimento del canale (noto anche come ID di conferma dell'ordine)
- ID fattura

Se viene trovata una transazione o un ordine che corrisponde ai criteri di ricerca, viene visualizzata la pagina **Prodotti restituibili**. In questa pagina gli utenti possono specificare gli articoli che vengono restituiti. Possono anche immettere quantità di reso e codici motivo.

Per ogni riga d'ordine nell'elenco dei prodotti restituibili, POS mostra le informazioni sulla quantità di acquisto originale e le quantità di eventuali resi precedentemente elaborati. La quantità di reso che un utente immette per una riga d'ordine deve essere inferiore o uguale al valore del campo **Disponibile per il reso**.

![Pagina dei prodotti restituibili.](media/returnslist.png)

Durante l'elaborazione del reso, se un utente ha il prodotto fisico e quel prodotto ha un codice a barre, l'utente può scansionare il codice a barre per registrare il reso. Ogni scansione del codice a barre aumenta la quantità di reso di un articolo. Tuttavia, se l'etichetta del codice a barre ha una quantità incorporata, tale quantità verrà inserita nel campo **Reso immediato**.

Gli utenti possono anche selezionare manualmente gli elementi da restituire nella pagina **Prodotti restituibili** per poi aggiornare il campo **Reso immediato** utilizzando il riquadro dei dettagli a destra.

Se viene specificata la quantità massima disponibile per **Reso immediato** per una transazione, l'utente può selezionare l'operazione **Seleziona tutto** sulla barra dell'app POS per impostare la quantità massima restituibile su tutte le righe.

Per ogni riga con una quantità **Reso immediato**, l'utente deve selezionare un codice del motivo di reso utilizzando il pannello dei dettagli. Per i resi di transazioni cash-and-carry, i codici del motivo del reso sono configurati come codici informativi nel profilo della funzionalità del punto vendita. Per i resi degli ordini cliente, i codici del motivo del reso sono configurati nella pagina **Codici motivo del reso** in Dynamics 365 Commerce Headquarters.

Dopo aver impostato la quantità di reso e il codice motivo per ogni articolo che deve essere restituito, l'utente può selezionare l'operazione di **reso** sulla barra dell'app POS per procedere con l'elaborazione. Viene visualizzata la pagina della transazione POS, dove sono stati aggiunti al carrello gli articoli da restituire selezionati nella pagina precedente. Le quantità **Reso immediato** degli articoli vengono visualizzate come righe di quantità negative nella transazione e viene calcolato il rimborso totale.

Gli utenti possono aggiungere righe a una transazione di reso se stanno creando un ordine di scambio. Gli utenti possono anche aggiungere più articoli di reso ad hoc a una transazione di reso utilizzando l'operazione **Restituisci prodotto** per una riga di vendita con quantità positiva selezionata che è stata aggiunta.

> [!NOTE]
> L'operazione **Restituisci prodotto** in POS non fornisce alcuna convalida a fronte di alcuna transazione originale e consente il reso di qualsiasi prodotto. Pertanto, si consiglia di consentire solo agli utenti autorizzati di eseguire questa operazione o di richiedere l'override del gestore se viene utilizzata questa operazione.

Se al momento del pagamento è dovuto un rimborso, le organizzazioni possono configurare [criteri di rimborso del pagamento](refund_policy_returns.md) che limitano i metodi di pagamento utilizzabili per rimborsare i clienti. Se la transazione originale è stata pagata utilizzando una carta di credito, a seconda del sistema di elaborazione dei pagamenti e della configurazione del sistema, gli utenti potrebbero avere la possibilità di [emettere un rimborso sulla carta originale](dev-itpro/linked-refunds.md). In questo caso, il rimborso può essere elaborato senza che il cliente debba strisciare nuovamente la carta di credito. Il token di pagamento originale viene utilizzato per emettere il rimborso.

## <a name="other-return-options-in-pos"></a>Altre opzioni di reso in POS

Quando la funzione **Esperienza di elaborazione dei resi unificata in POS** è attivata, gli utenti possono anche usare l'operazione **Mostra giornale di registrazione** in POS per inizializzare un reso per una transazione cash-and-carry o un ordine cliente. Possono quindi selezionare una transazione nel giornale di registrazione per poi selezionare l'operazione **Reso** sulla barra dell'app POS. Questa operazione è disponibile solo se nell'ordine sono presenti righe restituibili. Avvia la stessa esperienza utente dell'operazione **Transazione di reso**.

Gli utenti possono anche utilizzare l'operazione **Richiama ordine** in POS per ricercare e richiamare gli ordini cliente. (Questa operazione non può essere utilizzata per le transazioni cash-and-carry). In questo caso, dopo aver selezionato un ordine cliente, l'operazione **Reso** sulla barra dell'app POS può essere utilizzata per avviare un reso per l'ordine cliente. Questa operazione è disponibile solo se nell'ordine sono presenti righe restituibili. Avvia la stessa esperienza utente dell'operazione **Transazione di reso** o **Mostra giornale di registrazione**.

## <a name="return-orders-are-posted-to-commerce-headquarters-as-sales-orders"></a>Gli ordini di reso vengono registrati in Commerce Headquarters come ordini cliente 

Quando la funzione **Esperienza di elaborazione dei resi unificata in POS** è attivata, tutti i resi creati in POS vengono scritti in Commerce Headquarters come ordini cliente con righe negative. Nelle versioni precedenti alla versione Commerce 10.0.20, gli utenti possono selezionare se gli ordini di reso devono essere registrati come ordini cliente con righe negative o se devono essere ordini di reso creati tramite il processo RMA. 

Nella funzione **Esperienza di elaborazione dei resi unificata in POS** , l'opzione per usare il processo RMA per creare resi in POS è stato deprecato. Dopo l'attivazione di questa funzionalità, tutti i resi verranno creati come ordini cliente con righe negative.

## <a name="offline-return-processing-improvements"></a>Miglioramenti all'elaborazione dei resi offline

Nella maggior parte dei casi, quando un reso viene elaborato in POS, il sistema tenta di effettuare una chiamata di servizio in tempo reale (RTS) a Commerce Headquarters per convalidare le quantità correnti disponibili per il reso. Questa convalida aiuta a prevenire scenari fraudolenti in cui un cliente tenta di restituire lo stesso articolo in più posizioni.

Per gestire le situazioni in cui la chiamata RTS non può essere effettuata a causa di problemi di rete o connettività, è stato messo in atto un processo per sincronizzare periodicamente i dati sulla quantità restituita da Commerce Headquarters al database del canale di un punto vendita. Questo monitoraggio del ritorno lato canale aiuta a garantire che le quantità **Disponibile per il reso** mostrate in POS siano ragionevolmente accurate, anche quando POS è offline. Garantisce inoltre che POS possa continuare a convalidare le informazioni lato canale per aiutare a prevenire resi fraudolenti.

Per utilizzare il processo di reso offline nel modo appropriato, le organizzazioni devono pianificare il processo batch **Aggiorna quantità di reso** in Commerce Headquarters in modo che venga eseguito frequentemente. Si consiglia di eseguire questo processo con la stessa frequenza del processo P che estrae nuove transazioni dai canali di Commerce in Commerce Headquarters.

Il processo **Aggiorna quantità di reso** calcola la quantità disponibile per il reso per tutti gli ordini cliente trovati in Commerce Headquarters. I dati calcolati dal processo devono quindi essere inviati ai database dei canali, in modo che i canali del punto vendita possano essere aggiornati. A questo scopo viene utilizzato il processo di distribuzione **Quantità reso** (1200). Poiché i dati sulla quantità restituibile vengono sincronizzati da Commerce Headquarters, se un reso viene elaborato in POS, ma non è possibile effettuare la chiamata RTS, POS può utilizzare le informazioni di reso lato canale per convalidare le quantità **Disponibile per il reso** per una determinata linea di vendita.

Quando non è possibile effettuare chiamate RTS e POS utilizza i dati lato canale per la convalida del reso, un messaggio di avviso informa gli utenti che stanno creando una restituzione "offline". Pertanto, sono consapevoli che la quantità **Disponibile per il reso** mostrata in POS potrebbe essere non aggiornata e non più accurata, a seconda della data dell'ultima elaborazione e della sincronizzazione con il canale del processo **Aggiorna quantità di reso**.

Ad esempio, un cliente ha elaborato di recente un reso per una riga d'ordine in un altro canale, ma i dati non sono ancora stati sincronizzati con i database del canale tramite il processo **Aggiorna quantità di reso**. Il cliente si reca quindi in un altro punto vendita e cerca di restituire nuovamente lo stesso articolo. In questo caso, se il punto vendita non può effettuare la chiamata RTS a Commerce Headquarters per ottenere i dati di reso in tempo reale, POS consentirà la restituzione dell'articolo. Tuttavia, l'utente viene avvisato che le informazioni utilizzate per convalidare il reso potrebbero non essere aggiornate. Il messaggio che l'utente riceve è solo un messaggio di avviso. Non impedisce all'utente di continuare a elaborare il reso.

Se le informazioni lato canale non sono aggiornate per qualche motivo e viene elaborato un reso offline per una quantità che supera l'effettiva quantità **Disponibile per il reso**, potrebbe essere generato un errore durante l'esecuzione della registrazione del rendiconto per creare la transazione in Commerce Headquarters.

> [!NOTE]
> Quando la funzione **Esperienza di elaborazione dei resi unificata in POS** è attivata, diventano disponibili nuove funzionalità opzionali che supportano la convalida dei resi dei prodotti con numeri di serie. Per ulteriori informazioni, vedere [Restituire prodotti controllati dal numero di serie in POS](POS-serial-returns.md).

## <a name="enable-proper-tax-calculation-for-returns-with-partial-quantity"></a>Abilita il calcolo delle imposte corretto per i resi con quantità parziale

Questa funzione garantisce che quando un ordine viene restituito utilizzando più fatture, le imposte saranno pari all'importo delle imposte addebitato in origine.
1.  Accedere all'area di lavoro **Gestione funzionalità** e cercare **Abilita il calcolo delle imposte corretto per i resi con quantità parziale**.
2.  Selezionare **Abilita il calcolo delle imposte corretto per i resi con quantità parziale** e quindi fare clic su **Abilita**.


## <a name="additional-resources"></a>Risorse aggiuntive

[Restituire prodotti controllati dal numero di serie in POS](POS-serial-returns.md)

[Rimborsi collegati di transazioni precedentemente approvate e confermate](dev-itpro/linked-refunds.md)

[Creare e aggiornare i criteri per resi e rimborsi di un canale](refund_policy_returns.md)

[Configurazioni visive dell'interfaccia utente POS](pos-screen-layouts.md)
