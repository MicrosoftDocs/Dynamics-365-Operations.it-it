---
title: Pagamenti cliente per un importo parziale
description: Talvolta i clienti effettuano un pagamento inferiore rispetto all'importo della fattura. Questo articolo descrive le varie opzioni per gestire questa situazione. Le opzioni disponibili dipendono dai requisiti aziendali e dalla configurazione.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 01/08/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPaymEntry
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13011
ms.assetid: 20423a2d-6997-4e1c-a596-a77016600071
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a74803d3adf71ef1495ec5b42753d0988cea4133
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444647"
---
# <a name="customer-payments-for-a-partial-amount"></a>Pagamenti cliente per un importo parziale

[!include [banner](../includes/banner.md)]

Talvolta i clienti effettuano un pagamento inferiore rispetto all'importo della fattura. Questo articolo descrive le varie opzioni per gestire questa situazione. Le opzioni disponibili dipendono dai requisiti aziendali e dalla configurazione.

<a name="partial-payment-with-no-discount"></a>Pagamento parziale senza sconto
--------------------------------

I clienti possono effettuare un pagamento parziale perché non dispongono dei contanti sufficienti a pagare l'intera fattura o perché è aperta una controversia relativamente a un articolo in fattura. In questo caso, la fattura può essere liquidata parzialmente con il pagamento. La fattura rimarrà aperta e indicherà un saldo.

## <a name="discount-amounts"></a>Importi di sconto
È possibile offrire a clienti uno sconto di cassa se il pagamento di una fattura avviene prima della data di scadenza. Si supponga, ad esempio, di immettere una fattura per un valore 100,00 in cui si specifica uno sconto di cassa del 2% se la fattura viene pagata entro 10 giorni. I termini della data di scadenza sono a 30 giorni. Se si riceve un pagamento di 98,00 entro 10 giorni, si immette un pagamento di 98,00. Quindi, quando la fattura viene contrassegnata per la liquidazione, lo sconto di cassa viene applicato automaticamente.

## <a name="partial-payments-with-cash-discounts"></a>Pagamenti parziali con sconti di cassa
Quando i clienti effettuano un pagamento parziale, possono pianificare di effettuare un pagamento parziale aggiuntivo per liquidare interamente la fattura. Per applicare uno sconto di cassa per un pagamento parziale, è necessario impostare l'opzione **Calcola sconti di cassa per pagamenti parziali** su **Sì** nella pagina **Parametri contabilità clienti**. 

Si supponga, ad esempio, di offrire uno sconto di cassa del 2% se la fattura viene pagata entro 10 giorni dalla data di emissione. Si supponga che l'importo della fattura registrata sia 100,00. Se si riceve un pagamento di 49,00 entro 10 giorni, nel giornale di registrazione pagamenti verrà immesso un importo in Avere di 49,00. Quando viene liquidato il pagamento parziale nella pagina **Liquida transazioni**, viene visualizzato **1,00** nel campo **Importo sconto di cassa da applicare**. L'importo dello sconto viene registrato in un conto dello sconto di cassa. 

> [!NOTE] 
> Se si immette un pagamento parziale e si lascia l'intero importo della fattura nel campo **Importo da liquidare**, il campo **Importo sconto di cassa da applicare** viene automaticamente ricalcolato quando si registrano le transazioni.

## <a name="credit-notes-with-discounts"></a>Note di accredito con sconti
Se un cliente restituisce alcuni articoli di una fattura, è possibile emettere una nota di accredito. Se nella fattura originale era stato applicato uno sconto di cassa, la nota di credito al cliente deve essere emessa al netto dello sconto di cassa applicato al cliente. Se l'opzione **Calcola sconti di cassa per note di accredito** è impostata su **Sì** nella pagina **Parametri contabilità clienti**, lo sconto viene automaticamente calcolato per la nota di credito. 

Si supponga, ad esempio, di aver applicato dei termini di pagamento in cui viene specificato uno sconto del 2% se la fattura viene pagata entro 10 giorni dalla data di emissione. È stata registrata una fattura per 100,00 e il cliente ha ricevuto lo sconto di cassa. Se il cliente restituisce le merci a fronte dell'emissione di una nota di accredito, è possibile immettere la nota di accredito inserendo una transazione per -100,00. Quando si visualizza la nota di credito nella pagina **Liquida transazioni aperte**, viene visualizzato **98,00** nel campo **Importo da liquidare** e viene visualizzato **-2,00** nel campo **Importo sconto di cassa**. L'importo dello sconto viene registrato in un conto dello sconto di cassa.

## <a name="overpaymentunderpayment-amounts"></a>Importi per eccedenza/insufficienza di pagamento
È possibile che venga effettuato un pagamento parziale in cui l'importo che deve essere ancora liquidato è molto piccolo. Si supponga, ad esempio, di fatturare al cliente 1.000,00 e di ricevere un pagamento per 999,90. Se l'importo rimanente è inferiore all'importo specificato per le eccedenze o le insufficienze di pagamento nella pagina **Parametri contabilità clienti**, la differenza verrà registrata automaticamente in un conto CoGe per l'eccedenza/insufficienza di pagamento.

## <a name="full-settlement"></a>Liquidazione totale
I clienti possono effettuare un pagamento parziale in cui l'importo rimanente non verrà pagato ma è superiore aall'importo di pagamento insufficiente specificato nella pagina **Parametri contabilità fornitori**. Se si desidera contrassegnare la fattura come completamente liquidata, è possibile utilizzare l'opzione **Liquidazione totale** nella pagina **Liquida transazioni**. È possibile attivare la funzionalità di liquidazione completa utilizzando una chiave di configurazione. Ad esempio, una fattura viene registrata per 1.000,00 e il cliente effettua un pagamento di 990,00. Si è concordato che il cliente non deve pagare i 10,00 rimanenti. Dopo aver selezionato la fattura per la liquidazione, è possibile anche contrassegnare **Liquidazione totale**. La fattura verrà considerata interamente liquidata. La differenza di 10,00 verrà registrata in un conto dello sconto di cassa come ulteriore importo di sconto di cassa.


Per ulteriori informazioni, vedere [Depositare pagamenti clienti](tasks/deposit-customer-payments.md).
