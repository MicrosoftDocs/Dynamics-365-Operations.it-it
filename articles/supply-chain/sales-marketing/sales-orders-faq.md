---
title: Domande frequenti sugli ordini cliente
description: Questa pagina risponde alle domande frequenti che emergono quando si lavora con gli ordini cliente in Dynamics 365 Supply Chain Management.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: SalesTable, SalesTableListPage, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: d75022dcc476052040b16c9033cf5ff2a697ae6c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476759"
---
# <a name="sales-order-faqs"></a>Domande frequenti sugli ordini cliente

Questa pagina risponde alle domande frequenti che emergono quando si lavora con gli ordini cliente in Dynamics 365 Supply Chain Management.

## <a name="can-i-link-a-purchase-order-to-a-sales-order-to-fulfill-demand"></a>Posso collegare un ordine fornitore a un ordine cliente per soddisfare la domanda?

Puoi creare un ordine fornitore da un ordine cliente. Per ulteriori informazioni, vedi [Creare un ordine fornitore da un ordine cliente](/dynamics365/supply-chain/sales-marketing/tasks/create-purchase-order-sales-order).

## <a name="can-i-cancel-or-delete-a-sales-order-or-return-order"></a>Non posso annullare o eliminare un ordine cliente o un ordine di reso?

Puoi annullare solo gli ordini cliente e gli ordini di reso che si trovano in uno stato *Creato*. Per ulteriori informazioni, vedi [Annullare un ordine di reso](/dynamics365/supply-chain/service-management/cancel-return-order).

## <a name="can-i-restore-an-invoiced-sales-order-that-was-deleted"></a>Posso ripristinare un ordine cliente fatturato che è stato eliminato?

Se un ordine cliente fatturato è stato eliminato per errore, puoi ripristinarlo o visualizzarne i dettagli.

Vai a **Conto cliente \> Transazioni \> Documento originale \> Visualizza dettagli**. Trova la fattura che stai cercando e selezionala per visualizzarne i dettagli. Questi dettagli includono il riferimento dell'ordine cliente. Dovresti anche essere in grado di accedere ai dettagli dell'ordine cliente da quella pagina.

## <a name="how-do-i-delete-orphaned-sales-order-records"></a>Come eliminare i record degli ordini cliente orfani?

Per pulire i record degli ordini cliente orfani, esegui il processo periodico *Eliminazione dell'ordine cliente* andando in una delle seguenti posizioni:

- Vendite e marketing \> Attività periodiche \> Pulisci \> Elimina ordini cliente
- Vendita al dettaglio e commercio \> Vendita al dettaglio e commercio IT \> Pulisci \> Elimina ordini cliente

## <a name="is-there-a-way-to-calculate-commissions-on-invoices-that-have-already-been-posted"></a>Esiste un modo per calcolare le commissioni sulle fatture già registrate?

Supply Chain Management non supporta attualmente il calcolo delle commissioni per le fatture registrate.
