---
title: Collaborazione fornitore con i clienti
description: In questo argomento viene descritto come utilizzare la collaborazione fornitore in Finance and Operations per gestire gli ordini fornitore e monitorare l'inventario spedizione.
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ConsignmentProductReceiptLines, ConsignmentVendorPortalOnHand, PurchVendorPortalConfirmedOrders, PurchVendorPortalOriginalOrder, PurchVendorPortalResponsesHistoryList, PurchVendorPortalResponsesPart
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 221234
ms.assetid: 6e69fb8b-6d3a-46ef-88cf-6d01212aa7c3
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 69eeb90387ca5765c163c7d482295ea104cc078c
ms.openlocfilehash: 6119f1c85b68e6ed5dce01a266c4e681dfc4cd30
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="vendor-collaboration-with-customers"></a>Collaborazione fornitore con i clienti

[!include[banner](../includes/banner.md)]


In questo argomento viene descritto come utilizzare la collaborazione fornitore in Finance and Operations per gestire gli ordini fornitore e monitorare l'inventario spedizione.

In questo argomento viene descritto come utilizzare la collaborazione fornitore per lavorare con i clienti in Microsoft Finance and Operations. Include informazioni su come monitorare e rispondere agli ordini fornitore e come monitorare l'inventario di spedizione. È inoltre possibile utilizzare la collaborazione fornitore per lavorare con le fatture. Per ulteriori informazioni, vedere [Area di lavoro fatturazione di collaborazione fornitore](../../financials/accounts-payable/vendor-portal-invoicing-workspace.md).

## <a name="working-with-purchase-orders"></a>Gestione degli ordini fornitore
L'area di lavoro **Conferma ordine fornitore** consente di rispondere agli ordini fornitore inviati per la revisione. Consente inoltre di visualizzare le informazioni sugli ordini fornitore in attesa dell'azione dal cliente e su quelli confermati, ma ancora aperti. Sono disponibili tre elenchi  nell'area di lavoro **Conferma ordine fornitore**:

-   **Ordini fornitore per la revisione** in questo elenco sono contenuti gli ordini fornitore inviati e in attesa di una risposta. Dopo la risposta, l'ordine fornitore viene rimosso dall'elenco. Se il cliente invia una nuova versione di ordine fornitore prima che si sia risposto alla precedente, solo l'ultima versione viene visualizzata.
-   **In attesa dell'azione del cliente** questo elenco consente di visualizzare gli ordini fornitore a cui si è risposto ma non ancora confermati dal cliente. Se l'ordine fornitore è stato accettato, è possibile monitorarlo in questo elenco finché lo stato non cambia in **Confermato**. Se l'ordine fornitore è stato rifiutato o accettato con modifiche, è possibile monitorarlo qui il cliente non invia una nuova versione.
-   **Apri ordini fornitore confermati** in questo elenco sono contenuti tutti gli ordini fornitore per il proprio conto con stato **Confermato**. Quando i prodotti o servizi completamente ricevuti rispetto all'ordine fornitore, questo viene rimosso dall'elenco.

Nel seguente elenco sono riportate le quattro pagine che è possibile utilizzare per la gestione degli ordini fornitore, di  cui due contengono le stesse informazioni degli elenchi nell'area di lavoro:

-   **Ordini fornitore per la revisione** (vedere sopra)
-   **Storico conferme fornitore per l'ordine fornitore** Questa pagina contiene tutti gli ordini fornitore e tutte le versioni degli ordini fornitore inviati al fornitore e tutte le risposte restituite dal fornitore.
-   **Apri ordini fornitore confermati** (vedere sopra)
-   **Tutti gli ordini fornitore confermati** - In questa pagina vengono forniti tutti gli ordini fornitore confermati, inclusi quelli in cui i prodotti o servizi sono stati ricevuti. È possibile utilizzare l'elenco per controllare per quali ordini fornitore inviare le fatture.

### <a name="responding-to-purchase-orders"></a>Risposta a ordini fornitore

Gli ordini fornitore che il cliente ha inviato per la revisione sono visibili nell'area di lavoro **Conferma ordine fornitore** e nella pagina **Ordini fornitore per la revisione**. Una volta che si apre un ordine fornitore, è possibile scegliere di accettarlo, rifiutarlo, o accettarlo con modifiche. Potrebbero essere presenti allegati nell'intestazione dell'ordine fornitore o nelle singole righe. È inoltre possibile allegare informazioni alla risposta nell'intestazione o nelle singole righe di ordine fornitore. Ad esempio, è possibile suggerire un articolo sostitutivo per una delle righe. È possibile visualizzare in anteprima e stampare un ordine fornitore come file PDF tramite l'opzione **Anteprima/Stampa**. È possibile visualizzare o nascondere le seguenti colonne di dimensione tramite l'azione **Visualizza dimensioni**: Sito, Magazzino, Colore, Dimensione, Stile, Configurazione. Se si utilizza l'opzione **Accetta con modifiche**, è possibile accettare o rifiutare singole righe. È inoltre possibile apportare le modifiche seguenti alle righe:

-   Modificare le date o quantità. Se si desidera aggiornare la data di consegna confermata per tutte le righe, utilizzare l'opzione nell'intestazione di ordine fornitore **Aggiorna date di consegna**.
-   Suddividere righe per date o quantità di consegna differenti
-   Sostituire un articolo. Per effettuare questa operazione, immettere una descrizione dell'articolo e il numero di articolo nel campo **Esterno** della sezione **Dettagli riga**.

Non è possibile modificare le informazioni relative a spese o prezzo, ma è possibile suggerire modifiche a questi utilizzando le note. Se il cliente invia una nuova versione di un ordine fornitore, questo presenterà un suffisso versione per indicare che si tratta di una versione modificata di un ordine fornitore comunicato in precedenza. La pagina **Storico conferme fornitore per l'ordine fornitore** consente di tenere traccia dello storico di ciascun ordine.

## <a name="monitoring-consignment-inventory"></a>Monitoraggio dell'inventario spedizione
Se si utilizza l'inventario spedizione, è possibile utilizzare l'interfaccia di collaborazione fornitore per visualizzare le informazioni nelle pagine seguenti:

-   **Ordini fornitore che utilizzano inventario spedizione** - Gli ordini fornitore per l'inventario di spedizione vengono generati quando il cliente assume la proprietà dell'inventario. Questi ordini fornitore di spedizione vengono visualizzati solo nella pagina **Ordini fornitore che utilizzano inventario spedizione**. Non sono inclusi nella pagina **Tutti gli ordini fornitore confermati**.
-   **Prodotti entrati da inventario spedizione** questa pagina elenca tutte le transazioni in cui la proprietà dei prodotti è stata trasferita alla società che consuma l'inventario. Queste informazioni possono essere utilizzate per la fatturazione al cliente.
-   **Inventario spedizione disponibile** questa pagina mostra l'inventario spedizione disponibile di proprietà della società che è disponibile nel magazzino del cliente.


<a name="see-also"></a>Vedere anche
--------

[Gestire gli utenti di collaborazione fornitore](manage-vendor-collaboration-users.md)




