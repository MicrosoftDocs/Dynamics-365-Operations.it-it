---
title: Collaborazione fornitore con i clienti
description: In questo argomento viene descritto come utilizzare la collaborazione fornitore per gestire gli ordini fornitore e monitorare l'inventario spedizione.
author: TaylorVH
manager: tfehr
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ConsignmentProductReceiptLines, ConsignmentVendorPortalOnHand, PurchVendorPortalConfirmedOrders, PurchVendorPortalOriginalOrder, PurchVendorPortalResponsesHistoryList, PurchVendorPortalResponsesPart, VendVendorProfileCard, PurchVendorPortalAllResponse, PurchVendorPortalPendingResponsesPart, PurchVendorPortalResponses, PurchVendorPortalConfirmedOpenOrdersPart
audience: Application User
ms.reviewer: roschlom
ms.custom: 221234
ms.assetid: 6e69fb8b-6d3a-46ef-88cf-6d01212aa7c3
ms.search.region: Global
ms.author: v-savanh
ms.search.validFrom: 2020-11-01
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 3b4e2d3e4b4fc27107e34cdf8f87e32d0f56f556
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5246671"
---
# <a name="vendor-collaboration-with-customers"></a>Collaborazione fornitore con i clienti

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

In questo argomento viene descritto come utilizzare la collaborazione fornitore per lavorare con i clienti in Microsoft Dynamics 365 Supply Chain Management. I fornitori possono eseguire una serie di processi aziendali dalle seguenti aree di lavoro:

- **Conferma ordine fornitore** - Controllare e rispondere agli ordini fornitore.
- **Offerta fornitore** - Visualizzare richieste di offerta (RdO) e rispondere immettendo le offerte.
- **Informazioni fornitore** - Visualizzare e aggiornare dati master del fornitore.
- **Fatturazione** - Utilizzare le fatture. In questo argomento non viene trattata l'area di lavoro **Fatturazione**. Per ulteriori informazioni su questa area di lavoro, vedere [Area di lavoro fatturazione di collaborazione fornitore](../../financials/accounts-payable/vendor-portal-invoicing-workspace.md).

I fornitori possono inoltre controllare le informazioni sull'inventario spedizione.

## <a name="working-with-pos-in-the-purchase-order-confirmation-workspace"></a>Lavorare con gli ordini fornitore nell'area di lavoro Conferma ordine fornitore

L'area di lavoro **Conferma ordine fornitore** consente di rispondere agli ordini fornitore che sono stati inviati per la revisione. Consente inoltre di visualizzare le informazioni sugli ordini fornitore in attesa dell'azione dal cliente e su quelli confermati ma ancora aperti.

Sono disponibili tre elenchi  nell'area di lavoro **Conferma ordine fornitore**:

- **Ordini fornitore per la revisione** - In questo elenco sono contenuti gli ordini fornitore inviati e in attesa di una risposta. Dopo la risposta, l'ordine fornitore viene rimosso dall'elenco. Se il cliente invia una nuova versione di ordine fornitore prima che si sia risposto alla versione precedente, viene mostrata solo l'ultima versione.
- **In attesa dell'azione del cliente** - Questo elenco mostra tutti gli ordini fornitore a cui si è risposto ma non ancora confermati dal cliente. Se l'ordine fornitore viene accettato, è possibile monitorarlo in questo elenco finché lo stato non cambia in **Confermato**. Se l'ordine fornitore viene rifiutato o accettato con modifiche, è possibile monitorarlo qui finché il cliente non invia una nuova versione.
- **Apri ordini fornitore confermati** - In questo elenco sono mostrati tutti gli ordini fornitore per il proprio conto con stato **Confermato**. Quando i prodotti o servizi completamente ricevuti rispetto all'ordine fornitore, questo viene rimosso dall'elenco.

È possibile utilizzare le seguenti pagine per lavorare con gli ordini fornitore:

- **Ordini fornitore per la revisione** - La pagina contiene le stesse informazioni in un elenco **Ordini fornitore per la revisione** nell'area di lavoro. Vedere le descrizioni in precedenza nell'argomento.
- **Storico conferme fornitore per l'ordine fornitore** – Questa pagina contiene tutti gli ordini fornitore e tutte le versioni di ordini fornitore inviati al fornitore. Sono incluse inoltre tutte le risposte restituite dal fornitore.
- **Apri ordini fornitore confermati** - La pagina contiene le stesse informazioni dell'elenco **Apri ordini fornitore confermati** nell'area di lavoro. Vedere le descrizioni in precedenza nell'argomento.
- **Tutti gli ordini fornitore confermati** - La pagina contiene tutti gli ordini fornitore che sono stati confermati. Gli ordini fornitore mostrati in questa pagina includono gli ordini fornitore di prodotti o servizi ricevuti. È possibile utilizzare l'elenco per controllare per quali ordini fornitore inviare le fatture.

### <a name="responding-to-pos"></a>Rispondere a un ordine fornitore

Gli ordini fornitore che il cliente ha inviato per la revisione sono mostrati nell'area di lavoro **Conferma ordine fornitore** e nella pagina **Ordini fornitore per la revisione**. Una volta che si apre un ordine fornitore, è possibile accettarlo, rifiutarlo, o accettarlo con modifiche. Potrebbero essere presenti allegati nell'intestazione dell'ordine fornitore o nelle singole righe. Inoltre, è possibile allegare informazioni alla risposta nell'intestazione o nelle singole righe di ordine fornitore. Ad esempio, è possibile suggerire un articolo sostitutivo per una delle righe.

È possibile visualizzare in anteprima e stampare un ordine fornitore come file PDF tramite l'opzione **Anteprima/Stampa**. È possibile visualizzare o nascondere le seguenti colonne di dimensione tramite l'azione **Visualizza dimensioni**: **Sito**, **Magazzino**, **Colore**, **Dimensione**, **Stile**, **Configurazione**. 

Se si utilizza l'opzione **Accetta con modifiche**, è possibile accettare o rifiutare singole righe. È inoltre possibile apportare le modifiche seguenti alle righe:

- Modificare le date o quantità. Per aggiornare la data di consegna confermata per tutte le righe, utilizzare l'opzione nell'intestazione di ordine fornitore **Aggiorna date di consegna**.
- Suddividere righe per date o quantità di consegna differenti.
- Sostituire un articolo. Immettere una descrizione dell'articolo e il numero di articolo nel campo **Esterno** della sezione **Dettagli riga**.

Non è possibile modificare le informazioni relative a spese o prezzo, ma è possibile utilizzare le note suggerire modifiche a questi.

Se il cliente invia una nuova versione di un ordine fornitore, questo presenterà un suffisso versione per indicare che si tratta di una versione modificata di un ordine fornitore inviato in precedenza. La pagina **Storico conferme fornitore per l'ordine fornitore** consente di tenere traccia dello storico di ciascun ordine.

## <a name="monitoring-consignment-inventory"></a>Monitoraggio dell'inventario spedizione

Se si utilizza l'inventario spedizione, è possibile utilizzare l'interfaccia di collaborazione fornitore per visualizzare le informazioni nelle pagine seguenti:

- **Ordini fornitore che utilizzano inventario spedizione** - Gli ordini fornitore per l'inventario di spedizione vengono generati quando il cliente assume la proprietà dell'inventario. Questo ordini fornitore di spedizione vengono visualizzati solo in questa pagina. Non sono inclusi nella pagina **Tutti gli ordini fornitore confermati**.
- **Prodotti entrati da inventario spedizione** - Questa pagina elenca tutte le transazioni in cui la proprietà dei prodotti è stata trasferita alla società che consuma l'inventario. Queste informazioni possono essere utilizzate per la fatturazione al cliente.
- **Inventario spedizione disponibile** - Questa pagina mostra l'inventario spedizione disponibile di proprietà della società che è disponibile nel magazzino del cliente.

## <a name="working-with-rfqs-in-the-vendor-bidding-workspace"></a>Utilizzo di richieste di offerta nell'area di lavoro Offerta fornitore

L'area di lavoro **Offerta fornitore** consente di visualizzare le richieste di offerta (RdO) a cui la società è stata invitata a rispondere. È inoltre possibile rispondere alle richieste di offerta. 

L'area di lavoro mostra inoltre tutte le richieste di offerta vinte o perse. Inoltre, se il sistema è configurato per il settore pubblico, l'area di lavoro mostra le richieste di offerta pubblicamente disponibili.

### <a name="viewing-rfqs"></a>Visualizzare le richieste di offerta

Aprire l'area di lavoro **Offerta fornitore** per accedere alle informazioni seguenti:

- Selezionare **Nuovi inviti di offerta** per visualizzare le richieste di offerta a cui la società è stata invitata a rispondere. Da questa posizione, è possibile visualizzare una RdO e avviare il processo di offerta. È inoltre possibile visualizzare le RdO modificate a cui una nuova offerta deve essere inviata.
- Selezionare **Offerte restituite** per visualizzare le richieste di offerta che il cliente ha restituito in modo che sia possibile immettere ulteriori informazioni o aggiornare l'offerta.
- Selezionare **Offre in corso** per visualizzare le richieste di offerta a cui l'utente o un contatto che rappresenta la società sta lavorando ma non che non sono ancora state inviate.
- Selezionare **Offerte concesse** per verificare se il cliente ha assegnato almeno una voce nell'offerta.
- Selezionare **Offerte perse** per visualizzare le offerte in cui tutte le righe sono state rifiutate.
- Selezionare il collegamento **Richiesta di offerta** per visualizzare un elenco di inviti della RdO del fornitore e di tutte le offerte inviate. Nella pagina **Richiesta di offerta** sono elencate tutte le richieste di offerta in cui un fornitore è stato coinvolto. È possibile cercare in base allo stato.
- Selezionare il collegamento **Offerte rifiutate** per visualizzare un elenco di tutte le richieste di offerta per cui il contatto del fornitore ha rifiutato di fornire un'offerta.

### <a name="working-with-rfqs-that-are-publicly-available"></a>Utilizzo delle richieste di offerta disponibili pubblicamente

Le persone che lavorano nel settore pubblico possono visualizzare le richieste di offerta aperte e scadute che sono state rese disponibili al pubblico.

- Selezionare il collegamento **Richieste di offerta pubblicate aperte** per visualizzare un elenco delle richieste di offerta aperte che sono state rese disponibili al pubblico. Una RdO aperta è una RdO non ancora scaduta. È possibile trovare la data e l'ora di scadenza nell'intestazione della RdO.

    Se si è stati invitati a fornire un'offerta, è possibile individuare la stessa RdO nella pagina **Nuovi inviti di offerta**. In alcuni casi, potrebbe essere necessario fare un'offerta per una RdO aperta, ma non si è stati invitati all'offerta. In questo caso, potrebbe essere possibile invitare se stessi, a condizione che il cliente abbia abilitato l'invito automatico per il caso RdO.

    Migliora l'accessibilità del collegamento **Apri richieste di offerta pubblicate** attivando la funzionalità **Visualizza il collegamento "Apri richieste di offerta pubblicate" come riquadro**. Questa funzione converte il collegamento in un riquadro e lo sposta in una posizione prominente, in modo che sia facile da trovare.

- Selezionare il collegamento **Richieste di offerta pubblicate chiuse** per visualizzare un elenco delle richieste di offerta chiuse che sono state rese disponibili al pubblico. La RdO chiusa una RdO scaduta. È possibile trovare la data e l'ora di scadenza nell'intestazione della RdO.

    Una RdO chiusa mostra tutte le offerte fornitore fino al livello di riga. Quando le offerte vengono assegnate o rifiutate, queste informazioni si riflettono nella RdO chiusa. Tutti gli allegati inclusi nell'offerta sono inoltre disponibili.

> [!NOTE]
> Questa funzionalità è disponibile solo se è abilitata la configurazione del settore pubblico.

### <a name="bidding"></a>Offerta

- Selezionare **Offerta** per avviare un'offerta per una RdO.

    Se la modifica è abilitata per i campi di offerta sulle intestazioni e sulle righe di una RdO, è possibile inserire l'offerta direttamente nella griglia della riga. È inoltre necessario prendere in considerazione eventuali informazioni aggiuntive sull'offerta da aggiungere nei dettagli della riga.

    Quando si inizia a lavorare a un'offerta, questa viene visualizzata nella sezione **Offre in corso**.

    In qualsiasi momento prima della data di scadenza, è possibile salvare un'offerta. È quindi possibile tornare successivamente per finalizzare e inviare l'offerta. Dopo aver inviato un'offerta, è possibile richiamarla e aggiornare in data di scadenza.

- Selezionare **Reimposta dalla RdO** per reimpostare i dati immessi per un'offerta e tornare alla richiesta di offerta originale. È possibile reimpostare l'intestazione o la riga.
- Selezionare **Aggiungi alternativa** o **Rimuovi alternativa** nella griglia della riga per utilizzare le alternative.

    Alcune RdO consentono delle offerte alternative. È possibile specificare le offerte alternative solo per le righe di tipo **Categoria**, poiché non è possibile aggiungere articoli specifici come alternative. 

- Selezionare **Allegato RdO** o **Allegato righe RdO** per aprire qualsiasi allegato che il cliente ha aggiunto a una RdO. Selezionare **Allegati offerta** o **Allegati riga di offerta** per caricare allegati insieme all'offerta.

    Potrebbero esserci questionari a cui rispondere prima di poter presentare un'offerta.

- Selezionare **Rifiuta** se non si desidera inviare un'offerta. Dopo aver selezionato **Rifiuta**, non è possibile richiamare l'azione e inserire un'offerta.

Se una RdO viene modificata, è necessario immettere una nuova offerta. È possibile trovare informazioni sulla modifica nella scheda **Modifiche** della pagina RdO. Le RdO modificate vengono visualizzate nella pagina **Nuovi inviti di offerta**.

## <a name="accessing-vendor-master-data-in-the-vendor-information-workspace"></a>Accedere ai dati master del fornitore nell'area di lavoro Informazioni fornitore

Come fornitore, è possibile accedere a parte delle informazioni che il cliente mantiene aggiornate nel record dei dati master fornitore. Di conseguenza, è possibile mantenere le informazioni aggiornate. Per aggiornare le informazioni, è necessario disporre del ruolo di amministratore fornitore (esterno).

Le informazioni accessibili sono il nome del fornitore, gli indirizzi, le informazioni di contatto, le persone di contatto e le loro informazioni di contatto, i numeri di identificazione, i numeri di partita IVA, le categorie di approvvigionamento che il fornitore è autorizzato a vendere al cliente e le informazioni sulle certificazioni.

## <a name="additional-resources"></a>Risorse aggiuntive

[Gestire gli utenti della collaborazione fornitore](manage-vendor-collaboration-users.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]