---
title: Rinunciare all'addebito di interessi o commissioni, ripristinarli o stornarli
description: Questo articolo illustra come rinunciare ad addebitare, ripristinare e stornare le spese per gli interessi e le commissioni.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustInterestJourList
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 59461
ms.assetid: 25ec29f3-e3ea-4abb-bf6b-f6240873b315
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1b5c92d6f3bb0bdc3fbadc9708350b5107e6cf37
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444801"
---
# <a name="waive-reinstate-or-reverse-interest-fees"></a>Rinunciare all'addebito di interessi o commissioni, ripristinarli o stornarli

[!include [banner](../includes/banner.md)]

Questo articolo illustra come rinunciare ad addebitare, ripristinare e stornare le spese per gli interessi e le commissioni.

È possibile utilizzare i pulsanti della scheda **Raccogli** nella pagina elenco **Tutti i clienti** per rinunciare a spese, ripristinarle o stornarle:

-   Le spese non addebitate vengono condonate. È possibile rinunciare all'addebito di una spesa se, ad esempio, un cliente contesta la spesa e non si desidera compromettere le buone relazioni commerciali con quel cliente.
-   Le spese ripristinate diventano di nuovo esigibili. È possibile ripristinare le spese di cui in precedenza si è rinunciato all'addebito. Potrebbe essere necessario ripristinare le spese se si determina che non dovevano essere eliminate.
-   Le spese stornate vengono rimosse dal conto di un cliente e non sono più esigibili. È possibile stornare le spese se, ad esempio, è stato selezionato un tasso di interesse non corretto per calcolare il totale dovuto da un cliente. È possibile utilizzare un processo separato per ricalcolare gli interessi e creare una nota d'interesse contenente nuove spese per il cliente.

Tutte queste azioni modificano una nota d'interesse. Una nota d'interesse è un documento aziendale con cui i clienti vengono informati dell'addebito di interessi o commissioni sul loro conto. Quando si stornano interessi o commissioni o si rinuncia al loro addebito viene creata automaticamente una nota di accredito o una fattura di rettifica per liquidare le spese. Se si ripristinano le spese non addebitate, viene creata automaticamente una fattura con l'importo in Dare per ripristinare le spese dovute dal cliente. Nella tabella riportata di seguito viene descritto il risultato di ciascuna azione.

| Azione                                                                                                                                                                                                            | Risultato per il cliente                                                                                             | Elaborazione                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Rinunciare all'addebito di note d'interesse complete insieme agli interessi e le commissioni in esse inclusi. - Oppure - Rinunciare all'addebito di commissioni o transazioni interessi selezionate che fanno parte di note d'interesse.                                        | Le spese vengono condonate.                                                                                           | Viene creata una nota di accredito, o fattura di rettifica, per il cliente. La nota di accredito viene utilizzata per liquidare automaticamente la nota d'interesse oppure le transazioni interessi o le commissioni selezionate. L'importo liquidato corrisponde all'importo totale delle spese meno eventuali pagamenti precedenti effettuati dal cliente ed eventuali importi precedentemente annullati o non addebitati. Se l'importo della nota di accredito supera l'importo dovuto dal cliente, è possibile convertire la nota di accredito in fattura fornitore. Sarà quindi possibile effettuare un rimborso al cliente.                                                       |
| Ripristinare le note d'interesse complete insieme agli interessi e le commissioni in esse inclusi. - Oppure - Selezionare e ripristinare commissioni o transazioni interessi che fanno parte delle note d'interesse.                                | L'importo non addebitato diventa di nuovo esigibile.                                                                                     | Viene creata una fattura con un importo in Dare e l'importo viene automaticamente liquidato a fronte delle spese precedentemente non addebitate. Non vengono ripristinate le note d'interesse effettive. ma viene creata una fattura con l'importo dovuto dal cliente. Le note di accredito, o fatture di rettifica, create per liquidare le note d'interesse non addebitate, possono continuare a essere presenti se non sono state utilizzate per liquidare le note d'interesse. In tal caso, le note di accredito inevase vengono annullate. Le note di accredito inevase vengono in genere liquidate automaticamente quando si rinuncia all'addebito delle note d'interesse. È tuttavia possibile che sia presente una nota di accredito inevasa nel caso in cui un cliente abbia pagato una nota d'interesse contestandone le spese. |
| Stornare le note d'interesse complete. - Oppure - Stornare transazioni interessi selezionate che fanno parte di note d'interesse. **Nota:** non è possibile stornare una commissione. Tuttavia, è possibile stornare un'intera nota d'interesse che include una commissione. | Le spese non sono più dovute dal cliente. Le spese diventano però di nuovo esigibili se vengono ricalcolati gli interessi. | Il processo è analogo alla rinuncia al processo di addebito di note d'interesse o di transazioni interessi selezionate. Viene creata una nota di accredito, o fattura di rettifica, per il cliente. Tale nota di credito viene utilizzata per liquidare automaticamente la nota d'interesse. È possibile utilizzare un processo separato per ricalcolare gli interessi e creare una nuova nota d'interesse.                                                                                                                                                                                                                                                                                                                                                                                              |

> [!NOTE] 
> È inoltre possibile utilizzare un processo separato per annullare crediti a rischio. Questo processo consente di contrassegnare tutte le transazioni cliente per la liquidazione, anziché rinunciare solo alle spese che fanno parte delle note d'interesse.

## <a name="adjust-interest-for-invoices"></a>Rettificare gli interessi per le fatture
Oltre a rettificare le note d'interesse, è possibile rimuovere l'addebito interessi dalle fatture tramite uno dei processi seguenti. Entrambi i processi consentono di rettificare le note d'interesse correlate.

### <a name="correct-an-invoice-that-has-associated-interest"></a>Correggere una fattura con interessi associati

È possibile correggere una fattura registrata inclusa in una nota d'interesse. Questo processo copia i dettagli di una fattura esistente in una nuova fattura consentendo di apportare solo le correzioni desiderate. La fattura viene annullata e ne viene creata una nuova. Gli interessi sulla transazione vengono stornati nella nota d'interesse, se questa è stata registrata. 

È possibile apportare la correzione utilizzando il pulsante **Fattura corretta** nel riquadro azioni della fattura a testo libero. Questo pulsante è disponibile solo se è selezionata la chiave di configurazione **Correzione fattura a testo libero**.

### <a name="reverse-a-customer-transaction-that-has-associated-interest"></a>Stornare una transazione cliente con interessi associati

È possibile stornare una transazione cliente in una fattura se la fattura non è stata creata correttamente. Se la transazione cliente stornata include gli interessi di una nota d'interesse che è stata registrata, nella nota d'interesse vengono stornati anche gli interessi sulla transazione. Se non è stata registrata, la nota d'interesse viene annullata. 

È possibile stornare la transazione cliente utilizzando il pulsante **Storna** nella pagina **Transazioni cliente**.

## <a name="waive-or-reinstate-interest-notes"></a>Rinunciare all'addebito delle note d'interesse o ripristinarle
È possibile rinunciare all'addebito di tutte le spese nelle note d'interesse selezionate o ripristinarle. Quando si rinuncia ad addebitare delle spese, l'importo totale delle spese da non addebitare non può superare i limiti di importo impostati. È possibile ripristinare una nota d'interesse solo se in precedenza si è rinunciato all'addebito. 

È possibile rinunciare all'addebito delle note d'interesse o ripristinarle utilizzando il pulsante **Nota d'interesse** nella scheda **Raccogli** della pagina **Cliente**.

## <a name="waive-or-reinstate-interest-transactions"></a>Rinunciare all'addebito delle transazioni interessi o ripristinarle
È possibile rinunciare all'addebito di specifiche transazioni interessi di una nota d'interesse o ripristinarle anziché rettificare tutte le spese presenti in una nota d'interesse. Quando si rinuncia ad addebitare delle spese, l'importo totale delle spese da non addebitare non può superare i limiti di importo impostati. È possibile ripristinare una transazione interessi solo se in precedenza si è rinunciato all'addebito. 

È possibile rinunciare all'addebito delle note d'interesse o ripristinarle utilizzando il pulsante **Interessi transazione** nella scheda **Raccogli** della pagina **Cliente**.

## <a name="waive-or-reinstate-fees"></a>Rinunciare all'addebito di commissioni o ripristinarle
È possibile rinunciare all'addebito di specifiche commissioni di una nota d'interesse o ripristinarle anziché rettificare tutte le spese presenti nella nota d'interesse. Quando si rinuncia ad addebitare delle spese, l'importo totale delle spese da non addebitare non può superare i limiti di importo impostati. È possibile ripristinare una commissione solo se in precedenza si è rinunciato all'addebito. 

È possibile rinunciare all'addebito delle note d'interesse o ripristinarle utilizzando il pulsante **Commissioni** nella scheda **Raccogli** della pagina **Cliente**.

## <a name="reverse-interest-notes"></a>Storna note d'interesse
È possibile stornare tutte le spese presenti nelle note d'interesse selezionate. Le spese stornate vengono rimosse dal conto di un cliente e non sono più esigibili. Una volta stornata una nota d'interesse, è possibile ricalcolare gli interessi e creare una nuova nota d'interesse. 

È possibile stornare le note d'interesse utilizzando il pulsante **Nota d'interesse** nella scheda **Raccogli** della pagina **Cliente**.

## <a name="reverse-interest-transactions"></a>Stornare le transazioni interessi
È possibile stornare tutte le transazioni interessi selezionate. Le spese stornate vengono rimosse dal conto di un cliente e non sono più esigibili. Una volta stornate le transazioni, è possibile ricalcolare gli interessi e creare una nuova nota d'interesse.

È possibile stornare le transazioni interessi utilizzando il pulsante **Interessi transazione** nella scheda **Raccogli** della pagina **Cliente**.

## <a name="view-the-history-of-adjustments-for-charges-that-were-waived-reinstated-or-reversed"></a>Visualizzare lo storico delle rettifiche per le spese ripristinate, stornate o di cui si è rinunciato all'addebito
È possibile visualizzare lo storico dettagliato delle rettifiche effettuate per le note d'interesse, ad esempio l'utente che ha immesso la rettifica, il tipo di rettifica, l'importo e la data di immissione della rettifica. È possibile ad esempio visualizzare le rettifiche precedenti immesse per una nota d'interesse prima di creare una nuova nota d'interesse. 

È possibile stornare le transazioni interessi utilizzando il pulsante **Storico** nella scheda **Raccogli** della pagina **Cliente**.



