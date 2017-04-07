---
title: Collaborazione fornitore con i clienti
description: In questo argomento viene descritto come utilizzare la collaborazione fornitore in Microsoft Dynamics 365 for Operations per gestire gli ordini fornitore e monitorare l&quot;inventario spedizione.
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ConsignmentProductReceiptLines, ConsignmentVendorPortalOnHand, PurchVendorPortalConfirmedOrders, PurchVendorPortalOriginalOrder, PurchVendorPortalResponsesHistoryList, PurchVendorPortalResponsesPart
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 221234
ms.assetid: 6e69fb8b-6d3a-46ef-88cf-6d01212aa7c3
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 11cd2242b5a575ae87b0dbcf6f8ce268fcea5377
ms.lasthandoff: 03/31/2017


---

# <a name="vendor-collaboration-with-customers"></a>Collaborazione fornitore con i clienti

In questo argomento viene descritto come utilizzare la collaborazione fornitore in Microsoft Dynamics 365 for Operations per gestire gli ordini fornitore e monitorare l'inventario spedizione.

In questo argomento viene descritto come utilizzare la collaborazione fornitore per gestire i clienti in Microsoft Dynamics 365 for Operations. Sono riportate informazioni sul monitoraggio e rispondere agli ordini fornitore e su come verificare il magazzino di spedizione. È inoltre possibile utilizzare la relazione fornitore per utilizzare le fatture. Per ulteriori informazioni, vedere [relazione fornitore che fattura area di lavoro] (/dynamics365/operations/financials/accounts-payable/vendor-portal-invoicing-workspace).

## <a name="working-with-purchase-orders"></a>Gestione degli ordini fornitore
L'area di lavoro **Conferma ordine fornitore** consente di rispondere agli ordini fornitore inviati per la revisione. Consente inoltre di visualizzare le informazioni sugli ordini fornitore in attesa dell'azione dal cliente e su quelli confermati, ma ancora aperti. Sono disponibili tre elenchi  nell'area di lavoro **Conferma ordine fornitore**:

-   ** Gli ordini fornitore per la revisione ** - Questo elenco viene visualizzata l'ubicazione in cui sono stati inviati è in attesa di una risposta. Dopo che hanno, un ordine fornitore viene rimosso dall'elenco. Se il cliente invia una nuova versione di ordine fornitore prima che si sia risposto alla precedente, solo l'ultima versione viene visualizzata.
-   **In attesa dell'azione del cliente** questo elenco consente di visualizzare gli ordini fornitore a cui si è risposto ma non ancora confermati dal cliente. Se l'ordine fornitore è stato accettato, è possibile monitorarlo in questo elenco finché lo stato non cambia in **Confermato**. Se l'ordine fornitore è stato rifiutato o accettato con modifiche, è possibile monitorarlo qui il cliente non invia una nuova versione.
-   **Apri ordini fornitore confermati** in questo elenco sono contenuti tutti gli ordini fornitore per il proprio conto con stato **Confermato**. Quando i prodotti o servizi completamente ricevuti rispetto all'ordine fornitore, questo viene rimosso dall'elenco.

Nel seguente elenco sono riportate le quattro pagine che è possibile utilizzare per la gestione degli ordini fornitore, di  cui due contengono le stesse informazioni degli elenchi nell'area di lavoro:

-   **Ordini fornitore per la revisione** (vedere sopra)
-   **Storico conferme fornitore per l'ordine fornitore** Questa pagina contiene tutti gli ordini fornitore e tutte le versioni degli ordini fornitore inviati al fornitore e tutte le risposte restituite dal fornitore.
-   **Apri ordini fornitore confermati** (vedere sopra)
-   **Tutti gli ordini fornitore confermati** - In questa pagina vengono forniti tutti gli ordini fornitore confermati, inclusi quelli in cui i prodotti o servizi sono stati ricevuti. È possibile utilizzare l'elenco per controllare per quali ordini fornitore inviare le fatture.

### <a name="responding-to-purchase-orders"></a>Risposta a ordini fornitore

Gli ordini fornitore che il cliente ha concesso inviato a revisione sono visibili ** conferme ordini fornitore ** nell'area di lavoro e ** ordini fornitore per l'esame ** nella pagina. Una volta che si apre un ordine fornitore, è possibile scegliere di accettarlo, lo rifiuta, o lo accettate con le modifiche. Potrebbero essere presenti allegati nell'intestazione dell'ordine fornitore o nelle singole righe. È inoltre possibile allegare informazioni alla risposta nell'intestazione o nelle singole righe di ordine fornitore. Ad esempio, è possibile suggerire un articolo sostitutivo per una delle righe. È possibile visualizzare in anteprima e stampare un ordine fornitore come file PDF tramite l'opzione **Anteprima/Stampa**. È possibile visualizzare o nascondere le seguenti colonne di dimensione tramite l'azione **Visualizza dimensioni**: Sito, Magazzino, Colore, Dimensione, Stile, Configurazione. Se si utilizza ** accettare con le modifiche ** l'opzione, è possibile accettare o rifiutare singole righe. È inoltre possibile apportare modifiche alle seguenti righe:

-   Modificare le date o quantità. Se si desidera aggiornare la data di consegna confermata per tutte le righe, utilizzare l'opzione nell'intestazione di ordine fornitore **Aggiorna date di consegna**.
-   Suddividere righe per date o quantità di consegna differenti
-   Sostituire un articolo. Per effettuare questa operazione, immettere una descrizione dell'articolo e il numero di articolo nel campo **Esterno** della sezione **Dettagli riga**.

Non è possibile modificare le informazioni relative a spese o prezzo, ma è possibile suggerire modifiche a questi utilizzando le note. Se il cliente invia una nuova versione di un ordine fornitore, questo presenterà un suffisso versione per indicare che si tratta di una versione modificata di un ordine fornitore comunicato in precedenza. La pagina **Storico conferme fornitore per l'ordine fornitore** consente di tenere traccia dello storico di ciascun ordine.

## <a name="monitoring-consignment-inventory"></a>Monitoraggio dell'inventario spedizione
Se si utilizza l'inventario spedizione, è possibile utilizzare l'interfaccia di collaborazione fornitore per visualizzare le informazioni nelle pagine seguenti:

-   ** Gli ordini fornitore che consumano le scorte di spedizione ** - ordini fornitore per le scorte di spedizione vengono generati quando il cliente ha la responsabilità di magazzino. Questi ordini fornitore di spedizione vengono visualizzati solo nella pagina **Ordini fornitore che utilizzano inventario spedizione**. Non sono inclusi nella pagina **Tutti gli ordini fornitore confermati**.
-   **Prodotti entrati da inventario spedizione** questa pagina elenca tutte le transazioni in cui la proprietà dei prodotti è stata trasferita alla società che consuma l'inventario. Queste informazioni possono essere utilizzate per la fatturazione al cliente.
-   **Inventario spedizione disponibile** questa pagina mostra l'inventario spedizione disponibile di proprietà della società che è disponibile nel magazzino del cliente.


<a name="see-also"></a>Vedere anche
--------

[Gestire gli utenti di collaborazione fornitore](manage-vendor-collaboration-users.md)


