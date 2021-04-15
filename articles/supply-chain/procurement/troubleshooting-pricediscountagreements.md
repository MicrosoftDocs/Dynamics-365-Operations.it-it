---
title: Risolvere problemi relativi a prezzi, sconti, accordi e ribassi
description: Questo argomento descrive come risolvere i problemi che potrebbero verificarsi mentre lavori con prezzi, sconti, accordi e ribassi.
author: SmithaNataraj
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 12bc3cbccb1577c278489f640299510b3ced17e7
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5811088"
---
# <a name="troubleshoot-prices-discounts-agreements-and-rebates"></a>Risolvere problemi relativi a prezzi, sconti, accordi e ribassi

Questo argomento descrive come risolvere i problemi che potrebbero verificarsi mentre lavori con prezzi, sconti, accordi e ribassi.

## <a name="i-cant-link-a-purchase-agreement-to-a-purchase-order-line-after-the-purchase-order-is-created"></a>Non riesco a collegare un contratto di acquisto a una riga dell'ordine fornitore dopo aver creato l'ordine fornitore.

Un contratto di acquisto deve essere associato a un ordine fornitore dopo aver creato l'ordine fornitore. In caso contrario, le righe dell'ordine fornitore non possono essere associate alle righe del contratto di acquisto.

## <a name="what-check-triggers-the-update-prices-and-discounts-entered-manually-or-external-document-message"></a>Quale controllo attiva il messaggio "Aggiorna prezzi e sconti inseriti manualmente o documento esterno"?

Quando si modifica la data di spedizione, è possibile che venga visualizzato un messaggio che indica "Aggiorna prezzi e sconti inseriti manualmente o documento esterno". Viene visualizzato questo messaggio perché, se la data di spedizione viene modificata, potrebbe essere attivato un accordo commerciale o di vendita diverso e potrebbe causare una variazione del prezzo. Una modifica alla data di spedizione può anche influire sui programmi di magazzino e su altre informazioni correlate.

Il messaggio viene attivato ogni volta che una delle date o alcuni altri parametri vengono modificati. Lo scopo del messaggio è assicurarsi di essere a conoscenza delle variazioni di prezzo che possono verificarsi a causa di tali cambiamenti.

Il messaggio è il prompt della valutazione dell'accordo commerciale (TAE). Per una descrizione completa, vedi [Criteri di valutazione degli accordi commerciali](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/trade-agreement-evaluation-policies-white-paper).

## <a name="a-purchase-order-receipt-doesnt-include-all-charges"></a>Una ricevuta dell'ordine fornitore non include tutti gli addebiti.

### <a name="reproduce-the-issue"></a>Riprodurre il problema

La seguente procedura mostra un modo per riprodurre il problema.

1. Nella pagina **Parametri di approvvigionamento**, nella scheda **Consegna**, assicurati che l'opzione **Genera spese sull'entrata prodotti** sia impostata su *Sì*.
1. Crea un ordine fornitore che includa le spese.
1. Conferma l'ordine fornitore.
1. Ricevi l'ordine fornitore.
1. Guarda il totale dell'entrata e confrontalo con il totale previsto.
1. Si noti che non tutte le spese sono incluse nella ricevuta dell'ordine fornitore.

### <a name="issue-resolution"></a>Risoluzione dei problemi

La risoluzione dipende dal modo in cui sono state configurate le spese varie. Per informazioni su come configurare le spese varie per soddisfare le tue esigenze, consulta il seguente post del blog: [Pubblicare spese varie al momento dell'entrata del prodotto](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).

## <a name="trade-agreement-prices-and-discounts-arent-applied-on-sales-or-purchase-order-lines-that-are-imported-through-data-management"></a>I prezzi e gli sconti degli accordi commerciali non vengono applicati alle righe dell'ordine fornitore o cliente importate tramite la gestione dei dati.

### <a name="issue-description"></a>Descrizione del problema

Gli accordi commerciali applicabili alle righe dell'ordine fornitore o cliente non vengono applicate alle righe importate tramite la gestione dei dati. Tuttavia, gli stessi accordi commerciali vengono applicati alle righe dell'ordine fornitore o cliente create manualmente.

### <a name="reason-for-the-issue"></a>Motivo del problema

Se le righe dell'ordine fornitore importate tramite la gestione dei dati includono già informazioni sui prezzi, l'accordo commerciale non verrà rivalutato per tali righe. Ad esempio, se **Percentuale sconto riga** o uno qualsiasi dei valori di prezzo e sconto è impostata per una riga, gli accordi commerciali non verranno cercati per quella riga.

### <a name="issue-workaround"></a>Soluzione del problema

Questo comportamento è previsto ed è simile sia per gli ordini cliente che per gli ordini fornitore.

Come soluzione alternativa, importa le righe dell'ordine fornitore senza impostare alcuna informazione sul prezzo. Gli accordi commerciali verranno quindi applicati e le righe dell'ordine fornitore verranno aggiornate in base agli accordi commerciali definiti.

## <a name="a-vendor-rebate-isnt-cumulated-based-on-invoices"></a>Uno sconto fornitore non viene accumulato in base alle fatture.

### <a name="issue-description"></a>Descrizione del problema

Se le fatture registrate hanno date di scadenza diverse, tali fatture non vengono riflesse negli sconti fornitore generati da esse.

### <a name="issue-resolution"></a>Risoluzione dei problemi

In base alla progettazione, la data di scadenza non viene considerata quando viene calcolato lo sconto fornitore. Valuta la possibilità di personalizzare il sistema in modo che la data di scadenza e la relazione con la fattura siano più evidenti rispetto all'effettivo sconto fornitore.

## <a name="unit-prices-on-purchase-orders-arent-calculated-based-on-the-unit-conversion"></a>I prezzi unitari sugli ordini fornitore non vengono calcolati in base alla conversione delle unità.

### <a name="issue-description"></a>Descrizione del problema

Quando un'unità viene modificata in un ordine fornitore, i prezzi degli accordi commerciali non vengono ricalcolati in base alle definizioni di conversione delle unità.

### <a name="issue-resolution"></a>Risoluzione dei problemi

I prezzi sono sempre ottenuti da accordi commerciali (o altre impostazioni di prezzo nel sistema, come accordi di vendita o prezzi degli articoli) e sono impostati per un'unità.

Se l'unità viene modificata in una riga ordine, il sistema cerca un prezzo per la nuova unità e lo applica. Se non viene trovato alcun prezzo per l'unità, il sistema non applica un prezzo. La conversione di unità non può essere utilizzata per ricalcolare il prezzo in un'altra unità. In teoria, il prezzo per una scatola da dieci potrebbe non essere uguale a dieci volte il prezzo di una scatola.

### <a name="issue-workaround"></a>Soluzione del problema

Un modo per risolvere questo problema è assicurarsi che siano presenti accordi commerciali per le unità che si prevede verranno utilizzate nelle righe ordine per l'articolo.

## <a name="currency-conversion-issues-occur-with-trade-agreements"></a>Problemi di conversione di valuta si verificano con accordi commerciali.

I prezzi degli accordi commerciali non vengono ricalcolati in base alla valuta quando la valuta è diversa in un ordine fornitore.

La funzionalità *Valuta generica* consente di definire prezzi e sconti in una sola valuta. È quindi possibile convertire in altre valute come richiesto. Inoltre, al termine della conversione, la funzionalità può applicare automaticamente l'arrotondamento psicologico.

## <a name="when-i-open-the-purchase-agreement-page-in-a-line-view-mode-i-cant-personalize-the-page-by-adding-the-price-unit-field-in-the-overview-of-the-line"></a>Quando apro la pagina del contratto di acquisto in modalità di visualizzazione riga, non posso personalizzare la pagina aggiungendo il campo Unità di prezzo nella panoramica della riga.

Alcuni campi condivisi nel framework dell'accordo non possono essere inclusi nelle personalizzazioni. Questa limitazione si verifica a causa del modello di dati implementato. Pertanto, non è possibile personalizzare il campo **Unità di prezzo**.

## <a name="the-maximum-limit-from-a-purchase-agreement-isnt-effective-on-a-purchase-requisition"></a>Il limite massimo di un contratto di acquisto non è valido per una richiesta di acquisto.

### <a name="issue-description"></a>Descrizione del problema

Quando una richiesta di acquisto è collegata a un contratto di acquisto, il limite massimo del contratto di acquisto non è valido per la richiesta di acquisto. Le informazioni sul prezzo predefinito sono inserite correttamente, ma nella richiesta di acquisto è possibile ordinare più del limite massimo del contratto di acquisto.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Questo comportamento è previsto. Poiché le richieste non sono sempre approvate, una quantità o un importo non deve essere riservato nel contratto di acquisto. Pertanto, non raggiungerai il limite massimo del contratto di acquisto.

## <a name="trade-agreements-can-be-created-from-rejected-rfqs-therefore-the-system-doesnt-prevent-trade-agreement-journals-from-being-created-if-the-rfq-line-hasnt-been-accepted"></a>È possibile creare accordi commerciali da richieste di offerta rifiutate. Pertanto, il sistema non impedisce la creazione dei giornali di registrazione degli accordi commerciali se la riga RdO non è stata accettata.

È possibile creare accordi commerciali per qualsiasi risposta a una richiesta di offerta (RdO), indipendentemente dal fatto che sia stata accettata o rifiutata. Per ulteriori informazioni, vedi [Panoramica sulle richieste di offerta (RdO)](request-quotations.md).



[!INCLUDE[footer-include](../../includes/footer-banner.md)]