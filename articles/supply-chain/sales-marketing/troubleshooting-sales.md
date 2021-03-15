---
title: Risolvere i problemi relativi agli ordini cliente
description: Questo argomento descrive come risolvere i problemi che potresti riscontrare mentre lavori con gli ordini cliente.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTable, SalesTableListPage, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: c9a5b7a5e8cac7f8816233dd2d7ff1a7f84ea480
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974787"
---
# <a name="troubleshoot-sales-orders"></a>Risolvere i problemi relativi agli ordini cliente

Questo argomento descrive come risolvere i problemi che potresti riscontrare mentre lavori con gli ordini cliente.

## <a name="the-tax-information-isnt-updated-if-i-change-the-location-on-a-sales-order-header"></a>I dati fiscali non vengono aggiornati se cambio la posizione nell'intestazione di un ordine cliente.

### <a name="issue-description"></a>Descrizione del problema

Se il sito, il magazzino o l'indirizzo di consegna viene modificato nell'intestazione di un ordine cliente o a livello di riga, le informazioni sull'imposta del caso non vengono aggiornate automaticamente per le righe.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Questo comportamento è predefinito. Il problema si verifica perché anche l'indirizzo di consegna, il sito e il magazzino non vengono modificati automaticamente a livello di riga. È necessario aggiornarli manualmente.

## <a name="if-there-are-two-trade-agreements-for-the-same-period-or-overlapping-periods-the-same-agreement-line-is-always-selected"></a>Se sono presenti due accordi commerciali per lo stesso periodo o periodi sovrapposti, viene sempre selezionata la stessa riga dell'accordo.

### <a name="issue-description"></a>Descrizione del problema

Se due accordi commerciali sono definiti per lo stesso periodo o periodi sovrapposti, lo stesso accordo commerciale sembra essere selezionato ogni volta che si creano righe ordine cliente che contengono tali articoli.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Se è presente più di un accordo commerciale per una determinata data, viene sempre selezionato l'accordo commerciale con il prezzo più basso. Per altre informazioni, scarica il seguente white paper: [Accordi commerciali in Microsoft Dynamics AX 2012](https://www.axug.com/HigherLogic/System/DownloadDocumentFile.ashx?DocumentFileKey=3396a3a8-1f48-4d85-8cd6-5fa982f62e90).

## <a name="can-i-link-a-purchase-order-to-a-sales-order-to-fulfill-demand"></a>Posso collegare un ordine fornitore a un ordine cliente per soddisfare la domanda?

Puoi creare un ordine fornitore da un ordine cliente. Per ulteriori informazioni, vedi [Creare un ordine fornitore da un ordine cliente](tasks/create-purchase-order-sales-order.md).

## <a name="i-cant-cancel-or-delete-a-return-order-or-a-sales-order"></a>Non posso annullare o eliminare un ordine di reso o un ordine cliente.

Puoi annullare solo gli ordini cliente e gli ordini di reso che si trovano in uno stato *Creato*. Per ulteriori informazioni, vedi [Annullare un ordine di reso](../service-management/cancel-return-order.md).

## <a name="when-i-try-to-cancel-a-sales-order-i-receive-a-reservations-cannot-be-removed-because-there-is-work-created-which-relies-on-the-reservations-error"></a>Quando provo ad annullare un ordine client, ricevo un messaggio di errore "Impossibile rimuovere le prenotazioni perché è presente lavoro creato che si basa sulle prenotazioni".

Codice errore: WAX4661

Se il lavoro è associato a un ordine cliente, non è possibile annullare l'ordine cliente finché il lavoro non viene annullato e stornato. Questo requisito si applica anche se il lavoro associato all'ordine cliente viene chiuso.

Per risolvere questo problema, procedere come segue.

1. Annulla il lavoro e inserisci nuovamente le scorte nell'ubicazione desiderata. Vai al carico rilevante dell'ordine cliente e seleziona **Riduci quantità prelevata** sulla riga di carico o **Storna lavoro** nel riquadro azioni.

    Il lavoro ora ha uno stato di *Annullato* e viene creato ed elaborato automaticamente un nuovo lavoro di movimento scorte per reinserire le scorte nell'ubicazione descritta al momento dello storno.

2. Elimina il carico. Anche la spedizione viene eliminata.
3. Ora dovresti essere in grado di accedere all'ordine cliente e annullarlo.

## <a name="i-cant-cancel-an-intercompany-purchase-order-that-is-linked-to-a-sales-order"></a>Non riesco ad annullare un ordine fornitore interaziendale collegato a un ordine cliente.

### <a name="issue-description"></a>Descrizione del problema

Se tenti di annullare un ordine fornitore interaziendale collegato a un ordine cliente, è possibile che venga visualizzato il seguente messaggio di errore: "Impossibile ridurre la quantità perché la quantità di aggiornamento rimanente cambia segno".

### <a name="issue-resolution"></a>Risoluzione dei problemi

Questo problema è stato risolto in Microsoft Dynamics 365 Supply Chain Management versione 10.0.13. In quella versione e nelle versioni successive è ora possibile annullare un ordine fornitore interaziendale collegato a un ordine cliente.

## <a name="can-i-restore-an-invoiced-sales-order-that-was-deleted"></a>Posso ripristinare un ordine cliente fatturato che è stato eliminato?

### <a name="issue-description"></a>Descrizione del problema

Un ordine cliente fatturato è stato eliminato per errore e si desidera ripristinarlo o visualizzarne i dettagli.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Se l'ordine cliente eliminato è già stato fatturato, passa a **Account cliente \> Transazioni \>Documento originale \> Visualizza dettagli**. Trova la fattura che stai cercando e selezionala per visualizzarne i dettagli. Questi dettagli includono il riferimento dell'ordine cliente. Dovresti anche essere in grado di accedere ai dettagli dell'ordine cliente da quella pagina.

## <a name="the-deadline-of-a-sales-order-header-cant-be-found-in-the-salesorderheaderv2entity-data-entity"></a>La scadenza di un'intestazione di un ordine cliente non si trova nell'entità di dati SalesOrderHeaderV2Entity.

Il campo della scadenza non esiste nell'entità *SalesOrderHeaderV2Entity*.

## <a name="i-must-delete-orphaned-sales-order-records"></a>Devo eliminare i record degli ordini cliente orfani.

Per pulire i record degli ordini cliente orfani, esegui il processo periodico *Eliminazione dell'ordine cliente* andando in una delle seguenti posizioni:

- Vendite e marketing \> Attività periodiche \> Pulisci \> Elimina ordini cliente
- Vendita al dettaglio e commercio \> Vendita al dettaglio e commercio IT \> Pulisci \> Elimina ordini cliente

## <a name="is-there-a-way-to-calculate-commissions-on-invoices-that-have-already-been-posted"></a>Esiste un modo per calcolare le commissioni sulle fatture già registrate?

Supply Chain Management non supporta attualmente il calcolo delle commissioni per le fatture registrate.

## <a name="a-bundle-item-isnt-supported-in-an-intercompany-process"></a>Un articolo in aggregazione non è supportato in un processo interaziendale.

L'articolo in aggregazione non è disponibile per l'ordine fornitore perché, se esamini le righe dell'ordine cliente per l'articolo aggregato, noterai che la quantità è *0* (zero) e lo stato è *Annullato*. Questo comportamento è predefinito. L'ordine cliente acquista solo i componenti dell'articolo in aggregazione. Non acquista l'articolo in aggregazione stesso.

Se devi acquistare un'aggregazione, valuta se devi contrassegnarlo come articolo dell'aggregazione, perché questa funzionalità è progettata per scenari di riconoscimento dei ricavi. Per ulteriori informazioni su articoli e aggregazioni, vedi [Aggregazioni](../../finance/accounts-receivable/revenue-recognition-setup.md#bundles).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]