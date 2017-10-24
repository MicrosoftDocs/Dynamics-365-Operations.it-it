---
title: Risoluzione dei problemi dell'impostazione budget posizione
description: Questo articolo fornisce le risposte alle domande che potrebbero sorgere quando si configura il budget per la posizione. Risolve le domande frequenti sulla creazione degli elementi costo budget, i gruppi di retribuzione e le griglie retributive.
author: ryansandness
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: HcmBudgetPurposeType, HcmPositionForecast
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 88253
ms.assetid: c44df01b-8700-4022-b4c6-c4b1cb84d31d
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 421520fcd1b215a19c126ccea51b025977552448
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="position-budgeting-troubleshooting"></a>Risoluzione dei problemi dell'impostazione budget posizione

[!include[banner](../includes/banner.md)]


Questo articolo fornisce le risposte alle domande che potrebbero sorgere quando si configura il budget per la posizione. Risolve le domande frequenti sulla creazione degli elementi costo budget, i gruppi di retribuzione e le griglie retributive. 

<a name="why-cant-i-find-the-forecast-position-page-in-human-resources"></a>Perché non si trova la pagina Posizione prevista in Risorse umane?
---------------------------------------------------------------

Le posizioni previste sono state spostate in Impostazione budget.

## <a name="why-cant-i-delete-a-budget-cost-element"></a>Poiché è impossibile eliminare un elemento costo budget?
Non è possibile eliminare un elemento costo budget assegnato a una posizione di previsione. Prima di eliminare un elemento costo budget, è necessario rimuoverlo da tutte le posizioni previste. **Suggerimento:** per cercare tutte le posizioni a cui è assegnato un elemento costo budget, selezionare l'elemento di costo nella pagina **Elementi costo budget** e fare clic su **Aggiorna posizioni**. Le posizioni che utilizzano l'elemento costo vengono elencate nella griglia superiore.

## <a name="how-can-i-remove-a-cost-element-from-multiple-forecast-positions-without-opening-each-one"></a>Come posso rimuovere un elemento costo da più posizioni previste senza aprirle tutte?
Non è possibile rimuovere un elemento costo. Tuttavia, se si modificano le date di inizio e di fine in modo che l'elemento non rientri nelle date del ciclo di pianificazione del budget, l'elemento costo non sarà più assegnato alle posizioni previste in quel ciclo di pianificazione del budget. Per effettuare questa modifica, aprire l'elemento costo budget, nella scheda dettaglio **Calcolo costi** fare clic su **Modifica date** e modificare la data di validità o la data di scadenza. Fare clic su **OK** per aggiornare automaticamente tutte le posizioni previste a cui è assegnato l'elemento costo. **Suggerimento:** con questo metodo si rimuove l'elemento costo budget da **tutte** le posizioni previste per cui le date di inizio e di fine non si trovano più nell'intervallo appropriato. Se non si desidera che ciò avvenga, sarà necessario aprire ogni posizione prevista da cui si desidera rimuovere l'elemento costo budget ed eseguire la modifica manualmente.

## <a name="why-cant-i-enter-an-annual-amount-on-the-cost-calculation-fasttab-for-the-budget-cost-element"></a>Perché è impossibile immettere un importo annuale nella scheda dettaglio Calcolo costo dell'elemento costo budget?
Non è possibile immettere un importo annuale se sono presenti elementi costo budget nella scheda dettaglio **Base di calcolo**, perché il sistema richiede una percentuale per calcolare il valore. Per modificare il valore, rimuovere tutti gli elementi costo budget dalla scheda dettaglio **Base di calcolo**.

## <a name="why-cant-i-change-the-budget-cost-type-from-earning-to-another-budget-cost-type"></a>Perché è impossibile modificare il tipo di costo budget da "utili" a un altro tipo di costo budget?
Alcuni elementi costo budget utilizzano l'elemento costo "utili" come base di calcolo. Per modificare il campo **Tipo di costo budget**, rimuovere l'elemento costo "utili" dalla scheda dettaglio **Base di calcolo** di tutti gli elementi costo budget.

## <a name="why-cant-i-change-the-date-on-budget-cost-element-lines-for-a-budget-cost-element"></a>Perché è impossibile modificare la data nelle righe dell'elemento costo budget per un elemento costo budget?
Non è possibile modificare la data della riga dell'elemento costo budget che viene utilizzato da una posizione prevista. Ciò garantisce che le posizioni previste siano sempre conformi alle linee guida dell'elemento costo budget. Per modificare la data, nella scheda dettaglio **Calcolo costi** fare clic su **Modifica date** e immettere le nuove date. Fare clic su **OK** per aggiornare le posizioni previste a cui è assegnato l'elemento costo.

## <a name="why-cant-i-change-the-costs-for-a-budget-cost-element-on-the-compensation-group-page"></a>Perché è impossibile modificare i costi per un elemento costo budget nella pagina Gruppo di retribuzione?
È possibile creare e modificare gli elementi costo budget solo nella pagina **Elementi costo budget**.

## <a name="why-do-i-receive-an-error-message-when-i-change-the-dates-for-a-cost-element-on-a-forecast-position"></a>Perché viene visualizzato un messaggio di errore quando si modificano le date di un elemento costo in una posizione prevista?
Le date nella riga dell'elemento costo della posizione prevista devono rientrare nei seguenti intervalli:

-   Le date di attivazione e pensionamento della posizione.
-   Le date di attivazione e di scadenza dell'elemento costo budget.
-   Le date di inizio e di fine del ciclo di budget associato al processo di pianificazione del budget della posizione prevista.





