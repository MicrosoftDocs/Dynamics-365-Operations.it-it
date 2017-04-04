---
title: Pagamenti fornitore per un importo parziale
description: "Talvolta è possibile effettuare a un fornitore un pagamento inferiore rispetto all&quot;importo della fattura. Questo articolo descrive le varie opzioni per gestire questa situazione. Le opzioni disponibili dipendono dai requisiti aziendali e dalla configurazione."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14321
ms.assetid: 9a17075e-5325-4d55-a1e5-1791b8c460a0
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 2cb439e871d57f74c296697cfc42705fb0121bb7
ms.openlocfilehash: 4d243e6a9a68b69a6b32748344fc606ff3f2d965
ms.lasthandoff: 03/31/2017


---

# <a name="vendor-payments-for-a-partial-amount"></a>Pagamenti fornitore per un importo parziale

Talvolta è possibile effettuare a un fornitore un pagamento inferiore rispetto all'importo della fattura. Questo articolo descrive le varie opzioni per gestire questa situazione. Le opzioni disponibili dipendono dai requisiti aziendali e dalla configurazione. 

<a name="cash-discount-amounts"></a>Importi sconto di cassa
---------------------

È possibile che un fornitore applichi uno sconto di cassa se il pagamento di una fattura avviene prima della data di scadenza. Si supponga ad esempio di immettere una fattura per un valore 100,00 in cui si specifica uno sconto di cassa del 2% se la fattura viene pagata entro 10 giorni. I termini della data di scadenza sono pari a 30 giorni. Se una proposta di pagamento utilizza lo sconto di cassa come criterio per selezionare una fattura e se la proposta viene eseguita in o prima della data dello sconto di cassa, la fattura viene selezionata per il pagamento e il pagamento viene creato per 98.00. Sconto di cassa può essere applicato per un pagamento prodotti nelle commissioni di cui è stato creato manualmente.

## <a name="partial-payments-with-cash-discounts"></a>Pagamenti parziali con sconti di cassa
È possibile che venga effettuato un pagamento parziale liquidando interamente la fattura con un ulteriore pagamento parziale. Per ottenere uno sconto di cassa per un pagamento parziale, è necessario impostare ** calcolare gli sconti di cassa per i pagamenti parziali ** l'opzione ** Sì ** ** parametri di conto da pagare ** nella pagina. 

Si supponga ad esempio di ricevere uno sconto di cassa del 2% se la fattura viene pagata entro 10 giorni dalla data di emissione. Si supponga che l'importo della fattura registrata sia 100,00. Se si effettua un pagamento di 49.00 entro 10 giorni, si immette un importo in Dare di 49.00 in un giornale di registrazione pagamenti. Quando viene liquidato il pagamento parziale ** transazioni aperte liquidati ** nella pagina 1.00, ** ** ** viene visualizzato l'importo dello sconto di cassa da eseguire ** nel campo. 

> [!NOTE] 
> Se si immette un pagamento parziale e si lascia l'intero importo della fattura completo in ** importo da liquidare ** liquidate, ** importo dello sconto di cassa da eseguire ** il campo verrà ricalcolato automaticamente quando si registrano transazioni.

## <a name="credit-notes-with-cash-discounts"></a>Note di accredito con sconti di cassa
È possibile che vengano restituiti alcuni articoli di una fattura e che si riceva una nota di accredito. Se era stato applicato uno sconto di cassa alla fattura originale, è possibile sottrarre il valore dello sconto e ricevere un rimborso per l'importo corretto. ** Se per gli sconti di cassa per le note di accredito ** l'opzione è impostata su Sì ** ** ** parametri di contabilità fornitori ** nella pagina, lo sconto verrà calcolato automaticamente per la nota di accredito. 

Si supponga ad esempio di ricevere uno sconto di cassa del 2% se la fattura viene pagata entro 10 giorni dalla data di emissione. Si supponga che l'importo della fattura registrata sia 100,00. Se per le merci rese si riceve una nota di accredito, è possibile immettere la nota di accredito per l'intero importo della fattura originale, 100.00, insieme allo sconto di cassa del 2 che verrà definito nella nota di credito.  Nella nota di accredito ** transazioni liquidati ** nella pagina 98.00, ** ** visualizzato in ** importo da liquidare ** sistema e ** - 2.00 ** visualizzato in ** importi di sconto di cassa ** campo. L'importo dello sconto viene registrato in un conto dello sconto di cassa.

## <a name="overpaymentunderpayment-amounts"></a>Importi per eccedenza/insufficienza di pagamento
È possibile che venga effettuato un pagamento parziale in cui l'importo che deve essere ancora liquidato è molto piccolo. Ad esempio, la fattura fornitore è di 1.000,00 e il pagamento effettuato è pari a 999,90. Se l'importo rimanente è inferiore all'importo specificato per le eccedenze o insufficienze di pagamento nella pagina **Parametri contabilità clienti**, la differenza verrà registrata automaticamente in un conto CoGe per l'eccedenza/insufficienza di pagamento.


