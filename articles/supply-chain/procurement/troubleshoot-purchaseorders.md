---
title: Risolvere i problemi relativi agli ordini fornitore
description: Questo argomento descrive come risolvere i problemi che potresti riscontrare mentre lavori con gli ordini fornitore.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 234458f865e37a2d962aee8ab218b9521847081d
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "4431571"
---
# <a name="troubleshoot-purchase-orders"></a>Risolvere i problemi relativi agli ordini fornitore

Questo argomento descrive come risolvere i problemi che potresti riscontrare mentre lavori con gli ordini fornitore.

## <a name="an-action-can-be-completed-only-after-the-line-number-is-fully-distributed"></a>Un'azione può essere completata solo dopo che il numero di riga è stato completamente distribuito.

Questo problema può verificarsi a causa di incoerenze nelle distribuzioni degli ordini fornitore.

Per sbloccare questo problema e reimpostare l'ordine fornitore su uno stato *Bozza*, vai a **Approvvigionamento \>Attività periodiche \> Pulisci \> Reimpostazione distribuzione ordine fornitore**. Per ulteriori informazioni, vedi il seguente post del blog: [Risolvere gli errori di distribuzione dell'ordine fornitore in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

## <a name="when-purchase-orders-are-imported-through-data-management-purchase-order-line-numbers-dont-follow-the-increment-that-defined-in-system-parameters"></a>Quando gli ordini fornitore vengono importati tramite la gestione dei dati, i numeri di riga dell'ordine fornitore non seguono l'incremento definito nei parametri di sistema.

### <a name="issue-description"></a>Descrizione del problema

Per impostazione predefinita, i numeri di riga generati automaticamente per le righe ordine fornitore importate tramite l'entità di dati *Righe ordine fornitore V2* non utilizza l'incremento del numero di riga di sistema specificato nei parametri di sistema. Se crei manualmente un ordine fornitore e aggiungi righe tramite l'interfaccia utente (UI), i numeri di riga vengono incrementati correttamente. Tuttavia, se utilizzi Data Management Framework (DMF), non vengono incrementati correttamente.

Questo problema si verifica perché, quando si importano righe tramite DMF, se i numeri di riga non sono già assegnati nell'entità importata, il sistema utilizza il metodo DMF per assegnarli. Questo metodo incrementa sempre i numeri di riga di uno.

### <a name="issue-workaround"></a>Soluzione del problema

Accertarsi che i numeri di riga desiderati siano già specificati nei campi del numero di riga dell'entità di dati quando si importano le righe dell'ordine fornitore. In questo caso, DMF non sovrascriverà i numeri di riga.

## <a name="a-default-tax-group-and-a-default-cash-discount-arent-filled-in-from-the-invoice-account"></a>Un gruppo fiscale predefinito e uno sconto di cassa predefinito non vengono compilati dal conto fattura.

Se utilizzi un conto fattura diverso dal conto cliente, un gruppo fiscale predefinito e uno sconto di cassa predefinito non vengono compilati dal conto fattura quando viene creato un ordine fornitore.

Questo comportamento è predefinito. I valori predefiniti per il gruppo IVA, sconti di cassa e altre informazioni sui prezzi si basano sul conto cliente, non sul conto fattura.

## <a name="i-receive-an-object-reference-not-set-error-during-purchase-order-confirmation-or-an-exception-has-been-thrown-by-the-target-of-an-invocation-exception-occurs-during-vendor-invoice-posting"></a>Ricevo un errore "Riferimento oggetto non impostato" durante la conferma dell'ordine fornitore o un'eccezione "È stata generata un'eccezione dalla destinazione di una chiamata" durante la registrazione della fattura fornitore.

Questo problema può verificarsi a causa di incoerenze nelle distribuzioni degli ordini fornitore.

Per sbloccare questo problema e reimpostare l'ordine fornitore su uno stato *Bozza*, vai a **Approvvigionamento \>Attività periodiche \> Pulisci \> Reimpostazione distribuzione ordine fornitore**. Per ulteriori informazioni, vedi il seguente post del blog: [Risolvere gli errori di distribuzione dell'ordine fornitore in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

## <a name="one-or-more-accounting-distributions-are-either-over-distributed-or-under-distributed"></a>Una o più distribuzioni contabili è distribuita eccessivamente o sottodistribuita.

### <a name="issue-description"></a>Descrizione del problema

Viene visualizzato il seguente errore: "Una o più distribuzioni contabili è distribuita eccessivamente o sottodistribuita".

### <a name="issue-resolution"></a>Risoluzione dei problemi

Questo problema può verificarsi a causa di incoerenze nelle distribuzioni degli ordini fornitore.

Per sbloccare questo problema e reimpostare l'ordine fornitore su uno stato *Bozza*, vai a **Approvvigionamento \>Attività periodiche \> Pulisci \> Reimpostazione distribuzione ordine fornitore**. Per ulteriori informazioni, vedi il seguente post del blog: [Risolvere gli errori di distribuzione dell'ordine fornitore in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

## <a name="can-i-show-only-purchase-orders-that-i-created"></a>Posso mostrare solo gli ordini fornitore che ho creato?

Questa funzionalità non è attualmente disponibile.

## <a name="can-i-reserve-inventory-and-create-transactions-against-registered-inventory-on-a-purchase-order"></a>Posso prenotare scorte e creare transazioni a partire dall'inventario registrato in un ordine fornitore?

### <a name="issue-description"></a>Descrizione del problema

Anche quando gli articoli sono in uno stato *Registrato* su un ordine fornitore, è comunque possibile prenotare scorte. In altre parole, puoi creare transazioni a fronte dell'inventario registrato.

### <a name="reproduce-the-issue"></a>Riprodurre il problema

La seguente procedura mostra un modo per riprodurre il problema.

1. Creare un ordine fornitore.
2. Registra la riga relativa all'ordine fornitore.
3. Tieni presente che puoi generare prenotazioni o transazioni a fronte dell'inventario registrato.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Questo comportamento è predefinito. L'aspettativa è che gli articoli registrati siano fisicamente arrivati nel magazzino o nell'inventario e che siano quindi disponibili per la prenotazione.

## <a name="purchase-orders-dont-reflect-the-language-settings-of-the-legal-entity"></a>Gli ordini fornitore non riflettono le impostazioni della lingua della persona giuridica.

### <a name="issue-description"></a>Descrizione del problema

Il nome del prodotto in un ordine fornitore viene visualizzato nella lingua del sistema anziché nella lingua impostata per la persona giuridica in cui è stato creato l'ordine fornitore.

### <a name="reproduce-the-issue"></a>Riprodurre il problema

La seguente procedura mostra un modo per riprodurre il problema.

1. Imposta la lingua del sistema su *EN-US* (Inglese americano).
1. Assicurati che ci sia un prodotto in cui le lingue *EN-US* e *DE* (tedesco) vengono mantenute per le traduzioni del nome del prodotto.
1. Cambia la lingua di una persona giuridica in *DE*.
1. Nella persona giuridica dove *DE* è impostata come lingua, crea un ordine fornitore che includa il prodotto.
1. Si noti che il nome del prodotto è ancora visualizzato in inglese americano (la lingua del sistema).

### <a name="issue-resolution"></a>Risoluzione dei problemi

Questo comportamento è predefinito. Negli ordini fornitore, il prodotto viene sempre mostrato nella lingua del sistema. La lingua dell'ordine fornitore viene utilizzata quando viene creato un giornale di registrazione conferme.

## <a name="the-approved-vendor-list-by-product-entity-doesnt-allow-the-effective-date-to-be-changed"></a>L'elenco dei fornitori approvati per entità prodotto non consente la modifica della data di validità.

### <a name="issue-description"></a>Descrizione del problema

Un prodotto ha un fornitore approvato che ha, ad esempio, una data di validità dell'11 gennaio 2018 (*11/01/2018*) e una data di scadenza di *Mai*. Se provi a modificare la data di validità al 10 gennaio 2018 (*10/01/2018*) o il 12 gennaio 2018 (*12/01/2018*), viene visualizzato il seguente errore:

> Impossibile creare un record nell'elenco dei fornitori approvati (PdsApproveVendorList). Il valore "Scadenza" deve essere maggiore o uguale al valore "Validità".

### <a name="issue-resolution"></a>Risoluzione dei problemi

È possibile estendere solo il periodo per il quale il fornitore è approvato. Vengono applicate le seguenti regole:

- Per modificare la data di validità in modo che sia precedente a qualsiasi record (periodo) esistente per il fornitore dell'articolo, la data di scadenza del nuovo periodo deve essere precedente a tutte le date di scadenza nei record esistenti.
- Per modificare la data di scadenza in modo che sia successiva a uno qualsiasi dei periodi esistenti, la data di validità deve essere successiva all'ultima data di scadenza in qualsiasi record esistente.
- Per ridurre il periodo complessivo per il quale il fornitore è approvato, è necessario eliminare o modificare i record esistenti. In alternativa, puoi utilizzare l'interruttore **Tronca** durante l'importazione. Questa opzione elimina tutti i record esistenti nella tabella per i fornitori approvati per articolo.

Per lo scenario di esempio descritto nella descrizione del problema, in cui un record ha una data di validità di *11/01/2018* e una data di scadenza di *Mai*, puoi importare un nuovo record con data di validità *10/01/2018* e una data di scadenza di *Mai*. Tuttavia, non è possibile ridurre il periodo in modo che la data di validità venga aggiornata a *12/01/2018* tramite la gestione dei dati. È necessario apportare questa modifica tramite l'interfaccia utente.

## <a name="after-i-change-the-delivery-address-on-a-purchase-order-header-the-delivery-nameisnt-synced"></a>Dopo aver modificato l'indirizzo di consegna nell'intestazione di un ordine fornitore, il nome della consegna non viene sincronizzato.

### <a name="issue-description"></a>Descrizione del problema

L'indirizzo nell'intestazione di un ordine fornitore viene aggiornato su un indirizzo che non è un indirizzo di consegna. Sebbene l'indirizzo sia aggiornato nell'ordine fornitore, il nome della consegna non viene aggiornato in base all'indirizzo aggiornato.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Questo comportamento è predefinito. L'indirizzo selezionato deve essere classificato come indirizzo di consegna. In caso contrario, il nome della consegna non viene aggiornato in base all'indirizzo selezionato.

## <a name="can-i-find-the-user-who-canceled-a-purchase-order"></a>Posso trovare l'utente che ha annullato un ordine fornitore?

Questa informazioni viene registrata solo se per l'ordine fornitore è soggetto alla gestione delle modifiche. Se utilizzi la gestione delle modifiche, puoi vedere chi ha inviato la modifica (l'annullamento) e chi l'ha approvata.
