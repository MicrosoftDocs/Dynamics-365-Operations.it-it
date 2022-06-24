---
title: Aggiornare il budget riportabile in avanti dopo le riduzioni di ordini fornitore e fatture
description: Questo articolo descrive come controllare cosa accade al budget riportabile in avanti quando gli ordini fornitore vengono annullati o ridotti e quando le fatture vengono ridotte.
author: TaylorVH
ms.date: 02/11/2022
ms.topic: article
ms.search.form: LedgerFund
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-savanh
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2022-02-01
ms.openlocfilehash: 7f0ef0ffdf697609e811f754b4378b1f7a81c494
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8897960"
---
# <a name="update-the-carry-forward-budget-after-reductions-in-purchase-orders-and-invoices"></a>Aggiornare il budget riportabile in avanti dopo le riduzioni di ordini fornitore e fatture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Questo articolo descrive come controllare cosa accade al budget riportabile in avanti quando gli ordini fornitore vengono annullati o ridotti e quando le fatture vengono ridotte.

Per informazioni su come vengono elaborati gli ordini fornitore a fine anno, vedi [Elaborare gli ordini fornitore a fine anno](/dynamicsax-2012/appuser-itpro/process-purchase-orders-at-year-end).

## <a name="turn-carry-forward-budget-reductions-for-invoice-variances-on-or-off"></a>Attivare o disattivare le riduzioni del budget riportabile in avanti per gli scostamenti delle fatture

Il sistema può sempre aggiornare il budget riportabile in avanti quando un ordine fornitore viene annullato o ridotto. Tuttavia, se desideri aggiornare il budget riportabile in avanti quando una fattura viene ridotta, devi attivare la funzionalità *Riduci il budget riportabile in avanti quando la fattura di un ordine fornitore viene ridotta con uno scostamento*. Gli amministratori possono attivare o disattivare questa funzionalità nell'area di lavoro **[Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)**.

## <a name="purchase-order-reductions-and-cancellations"></a>Riduzioni e annullamenti degli ordini fornitore

Indipendentemente dal fatto che la funzionalità *Riduci il budget riportabile in avanti quando la fattura di un ordine fornitore viene ridotta con uno scostamento* è attivata, il budget riportabile in avanti verrà aggiornato quando un ordine fornitore idoneo viene annullato o ridotto. È possibile impostare ciascun fondo di contabilità generale in modo che risponda in uno dei seguenti modi:

- Conserva il budget riportabile in avanti così come è stato creato.
- Regola automaticamente il budget riportabile in avanti per rimuovere l'importo annullato o ridotto.

Solo le righe ordine fornitore con distribuzioni che includono un fondo sono disponibili per la rettifica automatica del budget. La rettifica automatica del budget si verifica quando l'ordine fornitore viene finalizzato o viene confermata una riduzione dell'ordine fornitore.

## <a name="invoice-reductions"></a>Riduzioni delle fatture

Quando la funzionalità *Riduci il budget riportabile in avanti quando la fattura di un ordine fornitore viene ridotta con uno scostamento* è attivata, è possibile specificare se ciascun fondo deve ridurre il budget riportabile in avanti quando viene ridotta una fattura, oltre che quando viene ridotto o annullato un ordine fornitore. La fattura deve essere relativa a un ordine fornitore con budget riportabile in avanti. Le riduzioni includono le variazioni di prezzo, le variazioni di addebito e le variazioni di imposta. Quando un ordine fornitore riportabile in avanti viene ridotto durante la fatturazione, viene creato uno scostamento. Al momento della registrazione della fattura, l'impegno di spesa dell'ordine fornitore verrà ridotto dell'importo dello scostamento. La funzione creerà anche la rettifica automatica del budget per l'importo dello scostamento.

Quando la funzionalità *Riduci il budget riportabile in avanti quando la fattura di un ordine fornitore viene ridotta con uno scostamento* è disattivata, il budget riportabile in avanti non viene ridotto in questo scenario. Pertanto, il restante budget riportabile in avanti per l'importo dello scostamento viene lasciato indietro.

## <a name="configure-the-carry-forward-budget-options-for-each-fund"></a>Configurare le opzioni di budget riportabile in avanti per ciascun fondo

Attieniti alla seguente procedura per ciascun fondo di contabilità generale che deve essere in grado di ridurre il budget riportabile in avanti quando un ordine fornitore o una fattura vengono ridotti.

1. Vai in **Contabilità generale \> Piano dei conti \> Fondi \> Fondi**.
1. Seleziona il fondo che vuoi creare.
1. Sotto **Processo di fine anno dell'ordine fornitore**, assicurati che l'opzione **Ignora opzione di fine anno selezionata** sia impostata su *sì*.
1. Sotto **Stato del budget riportabile in avanti**, imposta il campo **Ripristina il budget quando un ordine fornitore riportabile in avanti viene annullato o ridotto** come richiesto. Le impostazioni hanno effetti leggermente diversi, a seconda se la funzionalità *Riduci il budget riportabile in avanti quando la fattura di un ordine fornitore viene ridotta con uno scostamento* è attivata nel sistema.

    - Quando la funzione è disattivata, il sistema reagisce solo agli ordini fornitore annullati o ridotti. Le impostazioni dell'opzione funzionano nel modo seguente:

        - *No* – Il sistema crea una voce del registro di budget per il saldo residuo degli ordini fornitore che sono stati annullati o ridotti.
        - *sì* – Il sistema consente di annullare o ridurre gli ordini fornitore, ma non crea una voce di registro del budget. Il bilancio riportabile in avanti rimane disponibile per il consumo da parte di altri documenti.

    - Quando la funzione è attivata, il sistema reagisce sia agli scostamenti delle fatture che agli ordini fornitore annullati o ridotti. Le impostazioni dell'opzione funzionano nel modo seguente:

        - *No* – Per gli scostamenti di fattura, il sistema crea una voce del registro di budget rispetto all'ordine fornitore per l'importo di riduzione dello scostamento. Per gli ordini fornitore annullati o ridotti, questa impostazione ha lo stesso effetto che ha quando la funzione è disattivata.
        - *Sì* – Per gli scostamenti di fattura, il sistema consente la riduzione della fattura ma non crea una voce del registro di budget. Il bilancio riportabile in avanti rimane disponibile per il consumo da parte di altri documenti. Per gli ordini fornitore annullati o ridotti, questa impostazione ha lo stesso effetto che ha quando la funzione è disattivata.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Elaborare gli ordini fornitore alla fine dell'anno](/dynamicsax-2012/appuser-itpro/process-purchase-orders-at-year-end)
- [Gestisci prenotazioni di budget generale](general-budget-reservation-tasks.md)
- [Fondi nel settore pubblico](funds-public-sector.md)
- [Impostare un fondo nel settore pubblico](tasks/set-up-fund-public-sector.md)
