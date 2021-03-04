---
title: Pagamenti fornitore per un importo parziale
description: Talvolta è possibile effettuare a un fornitore un pagamento inferiore rispetto all'importo della fattura. Questo articolo descrive le varie opzioni per gestire questa situazione.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14321
ms.assetid: 9a17075e-5325-4d55-a1e5-1791b8c460a0
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 89e025977a0dcd40e35f17448a7b0ebde08cb6c8
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444618"
---
# <a name="vendor-payments-for-a-partial-amount"></a>Pagamenti fornitore per un importo parziale

[!include [banner](../includes/banner.md)]

Talvolta è possibile effettuare a un fornitore un pagamento inferiore rispetto all'importo della fattura. Questo articolo descrive le varie opzioni per gestire questa situazione. Le opzioni disponibili dipendono dai requisiti aziendali e dalla configurazione. 

<a name="cash-discount-amounts"></a>Importi sconto di cassa
---------------------

È possibile che un fornitore applichi uno sconto di cassa se il pagamento di una fattura avviene prima della data di scadenza. Si supponga ad esempio di immettere una fattura per un valore 100,00 in cui si specifica uno sconto di cassa del 2% se la fattura viene pagata entro 10 giorni. I termini della data di scadenza sono pari a 30 giorni. Se una proposta di pagamento utilizza lo sconto di cassa come criterio per selezionare una fattura e se la proposta viene effettuata il giorno della data dello sconto di cassa o prima, la fattura viene selezionata per il pagamento e il pagamento viene creato per un valore di 98,00. Uno sconto di cassa può anche essere applicato per un pagamento occasionale creato manualmente.

## <a name="partial-payments-with-cash-discounts"></a>Pagamenti parziali con sconti di cassa
È possibile che venga effettuato un pagamento parziale liquidando interamente la fattura con un ulteriore pagamento parziale. Per applicare uno sconto di cassa per un pagamento parziale, è necessario impostare l'opzione **Calcola sconti di cassa per pagamenti parziali** su **Sì** nella pagina **Parametri contabilità fornitori**. 

Si supponga ad esempio di ricevere uno sconto di cassa del 2% se la fattura viene pagata entro 10 giorni dalla data di emissione. Si supponga che l'importo della fattura registrata sia 100,00. Se si effettua un pagamento di 49,00 entro 10 giorni, nel giornale di registrazione pagamenti viene immesso un importo in Dare di 49,00. Quando viene liquidato il pagamento parziale nella pagina **Liquida transazioni aperte**, viene visualizzato **1,00** nel campo **Importo sconto di cassa da applicare**. 

> [!NOTE] 
> Se si immette un pagamento parziale e si lascia l'intero importo della fattura nel campo **Importo da liquidare**, il campo **Importo sconto di cassa da applicare** viene automaticamente ricalcolato quando si registrano le transazioni.

## <a name="credit-notes-with-cash-discounts"></a>Note di accredito con sconti di cassa
È possibile che vengano restituiti alcuni articoli di una fattura e che si riceva una nota di accredito. Se era stato applicato uno sconto di cassa alla fattura originale, è possibile sottrarre il valore dello sconto e ricevere un rimborso per l'importo corretto. Se l'opzione **Calcola sconti di cassa per note di accredito** è impostata su **Sì** nella pagina **Parametri contabilità fornitori**, lo sconto verrà calcolato automaticamente per la nota di accredito. 

Si supponga ad esempio di ricevere uno sconto di cassa del 2% se la fattura viene pagata entro 10 giorni dalla data di emissione. Si supponga che l'importo della fattura registrata sia 100,00. Se per le merci rese si riceve una nota di accredito, è possibile immettere la nota di accredito per l'intero importo della fattura originale, 100,00, insieme allo sconto di cassa del 2% che viene anche definito nella nota di accredito.  Quando si visualizza la nota di accredito nella pagina **Liquida transazioni aperte**, viene visualizzato **98,00** nel campo **Importo da liquidare** e viene visualizzato **-2,00** nel campo **Importo sconto di cassa**. L'importo dello sconto viene registrato in un conto dello sconto di cassa.

## <a name="overpaymentunderpayment-amounts"></a>Importi per eccedenza/insufficienza di pagamento
È possibile che venga effettuato un pagamento parziale in cui l'importo che deve essere ancora liquidato è molto piccolo. Ad esempio, la fattura fornitore è di 1.000,00 e il pagamento effettuato è pari a 999,90. Se l'importo rimanente è inferiore all'importo specificato per le eccedenze o insufficienze di pagamento nella pagina **Parametri contabilità clienti**, la differenza verrà registrata automaticamente in un conto CoGe per l'eccedenza/insufficienza di pagamento.


Per ulteriori informazioni, vedere [Panoramica pagamenti fornitore](../cash-bank-management/tasks/vendor-payment-overview.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]