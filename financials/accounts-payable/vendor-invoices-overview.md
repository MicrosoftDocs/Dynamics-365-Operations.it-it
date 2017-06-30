---
title: Panoramica delle fatture fornitore
description: Questo articolo fornisce informazioni generali sulle fatture fornitore. Le fatture fornitore sono obbligatorie per il pagamento dei prodotti e dei servizi ricevuti. Le fatture fornitore possono rappresentare una fattura per i servizi correnti oppure possono essere basate su ordini fornitore per articoli e servizi specifici.
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 13971
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 16ff8ebb0e620f45c4d290ee5076d5505abf3436
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="vendor-invoices-overview"></a>Panoramica delle fatture fornitore

[!include[banner](../includes/banner.md)]


Questo articolo fornisce informazioni generali sulle fatture fornitore. Le fatture fornitore sono obbligatorie per il pagamento dei prodotti e dei servizi ricevuti. Le fatture fornitore possono rappresentare una fattura per i servizi correnti oppure possono essere basate su ordini fornitore per articoli e servizi specifici. 

<a name="vendor-invoices"></a>Fatture fornitore
---------------

Una fattura fornitore da un ordine fornitore è una fattura generata quando i prodotti o servizi vengono ricevuti in base a un ordine fornitore che è stato emesso per un fornitore. La fattura fornitore contiene un'intestazione e una o più righe per articoli o servizi. Una fattura fornitore completa il ciclo dall'ordine fornitore all' entrata prodotti alla fattura fornitore. 

Sebbene alcune fatture fornitore siano collegate a un ordine fornitore, le fatture fornitore possono anche contenere righe che non corrispondono alle righe ordine fornitore. È anche possibile creare fatture fornitore non associate ad alcun ordine fornitore. Queste fatture fornitore potrebbero rappresentare i servizi in corso, ad esempio una fattura di utilità, e non è necessario fare riferimento a un ordine fornitore quando si aggiungono. 

Sono disponibili diversi modi di immettere una fattura fornitore:

-   Il registro fatture fornitore consente di immettere rapidamente le fatture che non fanno riferimento a un ordine fornitore, in modo da poter accumulare la spesa. Utilizzando il giornale di registrazione approvazioni fatture fornitore, è possibile selezionare le fatture e registrarle al saldo fornitore per stornare gli importi della competenza..
-   Il giornale di registrazione fatture fornitore consente di immettere rapidamente le fatture che non fanno riferimento a un ordine fornitore, in un unico passaggio.
-   Insieme al pool fatture fornitore, il registro fatture fornitore consente di immettere rapidamente fatture per accumulare la competenza. È possibile aprire successivamente gli ordini fornitore associati per registrare la fattura a fronte del conto spese.
-   Le pagine **Fatture fornitore aperte** e **Fatture fornitore in sospeso** consentono di creare fatture fornitore da ordini fornitore confermati.

La discussione seguente fornisce ulteriori informazioni su come utilizzare la pagina **Fatture fornitore aperte** o **Fatture fornitore in sospeso** per creare una fattura fornitore da un ordine fornitore.

## <a name="understanding-invoice-line-quantities"></a>Informazioni sulle quantità righe fattura
Quando si apre una fattura fornitore da un ordine fornitore correlato, righe fattura vengono create dall'ordine fornitore. Per impostazione predefinita, le quantità derivano dalla quantità di entrata prodotti. Tuttavia, è possibile utilizzare uno dei seguenti comportamenti predefiniti:

-   **Quantità in Ricevi ora** Utilizzare questa opzione per le spedizioni parziali. Il valore predefinito del campo **Quantità** deriva dal campo quantità **Ricevi ora** nell'ordine fornitore.
-   **Quantità ordinata** Utilizzare questa opzione per le spedizioni complete. Il valore predefinito del campo **Quantità** deriva dal campo quantità **Ordinata** nell'ordine fornitore.
-   **Quantità registrata** Utilizzare questa opzione se l'articolo richiede la registrazione, come specificato nella pagina **Gruppi di modelli di articoli**. Il valore predefinito nel campo **Quantità** è la quantità fisica di aggiornamento registrata.
-   **Quantità entrata prodotti**: utilizzare questa opzione se per l'ordine è già stata ricevuta un'entrata prodotti. Il valore predefinito nel campo **Quantità** deriva dalla quantità totale di entrate prodotti disponibili.
-   **Quantità registrata e servizi**: utilizzare questa opzione se le quantità sono state registrate nei giornali di registrazione arrivi per articoli stoccati o articoli non stoccati. In questa opzione sono inoltre inclusi i servizi, indipendentemente dal relativo stato di registrazione.

Se la persona giuridica utilizza l'abbinamento fatture, è possibile visualizzare i risultati degli abbinamenti quantità nella colonna **Abbinamento quantità entrata prodotti**. È anche possibile utilizzare il comando di menu **Dettagli corrispondenti** nella scheda **Revisione** per visualizzare i risultati degli abbinamenti quantità.

## <a name="adding-a-line-that-wasnt-on-the-purchase-order"></a>Aggiungere una riga non presente dell'ordine fornitore
È possibile aggiungere una nuova riga non presente nell'ordine fornitore alla fattura fornitore. È necessario selezionare un numero di articolo o una categoria di approvvigionamento. È possibile aggiungere le quantità, i prezzi e gli importi nella riga. La riga verrà inclusa solo nei criteri di abbinamento nei totali fattura.

## <a name="submitting-a-vendor-invoice-for-review"></a>Invio di una fattura fornitore per la revisione
L'organizzazione può utilizzare flussi di lavoro per gestire il processo di revisione per le fatture fornitore. La revisione del flusso di lavoro può essere necessaria per l'intestazione della fattura, per la riga di fattura o per entrambe. I controlli del flusso di lavoro vengono applicati all'intestazione o alla riga, a seconda della posizione dello stato attivo quando si fa clic sul controllo. Anziché il pulsante **Registra**, verrà visualizzato il pulsante **Invia** che può essere utilizzato per inviare la fattura fornitore tramite il processo di revisione.

## <a name="matching-vendor-invoices-to-product-receipts"></a>Abbinamento delle fatture fornitore con le entrate prodotti
È possibile immettere e salvare le informazioni relative alle fatture fornitore e abbinare le righe di fattura alle righe dell'entrata prodotti. È inoltre possibile abbinare quantità parziali per una riga 

È possibile creare una fattura fornitore basata sulle voci entrata prodotti ricevute fino alla data corrente, anche se non sono stati ancora ricevuti tutti gli articoli di un ordine fornitore specifico. È possibile ad esempio utilizzare questa opzione se un fornitore emette una fattura al mese per coprire tutte le consegne spedite nel mese in questione. Ogni entrata prodotti corrisponde a una consegna completa o parziale degli articoli inclusi nell'ordine fornitore. 

Quando viene registrata la fattura, la quantità **Rimanente fattura** relativa a ogni articolo viene aggiornata con il totale delle quantità ricevute, tratto dalle entrate prodotti selezionate. Se entrambe le quantità **Rimanente fattura** e **Rimanente consegna** per tutti gli articoli dell'ordine fornitore sono uguali a 0 (zero), lo stato dell'ordine fornitore passa a **Fatturato**. Se la quantità **Rimanente fattura** è diversa da 0 (zero), lo stato dell'ordine fornitore non viene modificato e per tale ordine è possibile immettere ulteriori fatture.

In questa opzione si presuppone che per l'ordine fornitore sia stata registrata almeno un'entrata prodotti. La fattura fornitore si basa sulle entrate prodotti e riflette le quantità in esse contenute. Le informazioni finanziarie per la fattura si basano sulle informazioni immesse al momento della registrazione della fattura stessa.

## <a name="working-with-multiple-invoices"></a>Utilizzo con più fatture

È possibile utilizzare più fatture e registrarle tutte contemporaneamente. Se è necessario creare più fatture, utilizzare la pagina **Fatture fornitore in sospeso**. Se è necessario registrare e stampare più fatture fornitore, utilizzare la pagina del giornale di approvazione fatture. Se si utilizza il giornale di approvazione fatture è necessario che sia registrata almeno un'entrata prodotti per l'ordine fornitore e che sia registrata una fattura per l'ordine fornitore in un registro fatture. Le informazioni finanziarie relative alla fattura derivano dalla fattura inserita nel registro.





