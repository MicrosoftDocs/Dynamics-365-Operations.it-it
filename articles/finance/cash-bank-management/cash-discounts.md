---
title: Sconti di cassa
description: Gli sconti di cassa vengono impostati e condivisi per la contabilità fornitori e la contabilità clienti.  Lo sconto di cassa disponibile può essere definito sulla fattura cliente o sulla fattura fornitore e verrà applicato se la fattura viene pagata entro la data dello sconto di cassa.
author: angelad116
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CashDisc
audience: Application User
ms.reviewer: kfend
ms.custom: 3741
ms.assetid: c25f9d85-2702-46aa-8e61-0b4886e069b3
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b75637bfb38c13591223ff11be36d958b3972d4f
ms.sourcegitcommit: 81bb8e51951395be3f18f45212e47e6c41656f6a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2022
ms.locfileid: "9804138"
---
# <a name="cash-discounts"></a>Sconti di cassa

[!include [banner](../includes/banner.md)]

Gli sconti di cassa vengono impostati e condivisi per la contabilità fornitori e la contabilità clienti. Lo sconto di cassa disponibile può essere definito sulla fattura cliente o sulla fattura fornitore e verrà applicato se la fattura viene pagata entro la data dello sconto di cassa. 

## <a name="cash-discounts"></a>Sconti di cassa

Gli sconti di cassa per entrambi i clienti o fornitori possono essere creati nella pagina **Sconti di cassa**. Utilizzando il campo **Codice sconto successivo** è inoltre possibile definire una serie di sconti di cassa che si succedono via via che gli sconti di cassa precedenti scadono. Per ulteriori informazioni, vedi "Esempio: Serie di sconti di cassa" più avanti in questo articolo. Se la fattura, la transazione in Avere (un pagamento oppure una nota di accredito) o entrambe sono immesse una valuta diversa da quella di contabilizzazione della persona giuridica, lo sconto di cassa è calcolato usando il tasso di cambio alla data del pagamento o della nota di accredito. Se la fattura e il documento di credito vengono inseriti in persone giuridiche diverse, e se le valute di contabilizzazione per le persone giuridiche differiscono, il tasso di cambio viene preso dalla persona giuridica della fattura, alla data del documento di credito. Per ulteriori informazioni, vedi "Esempio: Tassi di cambio per sconti di cassa" più avanti in questo articolo.

## <a name="defaulting-order-of-cash-discount-main-account"></a>Ordine predefinito del conto principale dello sconto di cassa

Se una fattura viene liquidata in tempo per ottenere uno sconto di cassa, questo verrà registrato automaticamente in un conto principale per sconti di cassa in base alle seguenti priorità di default:
1.  Il conto principale specificato nel campo **Conto sconto di cassa alternativo** sulla pagina **Liquida transazioni aperte** del cliente o **Liquida transazioni aperte** del fornitore.
2.  Il conto principale specificato nel campo **Sconto di cassa cliente** o nel campo **Sconto di cassa fornitore** del gruppo di registrazione contabile assegnato al codice IVA della fattura. Configurare gruppi di registrazione contabile nella pagina **Gruppi registrazione contabile** e assegnarli ai codici IVA nella pagina **Codici IVA**.
3.  Il conto di registrazione principale nella pagina **Sconti di cassa** nel campo **Conto principale per sconti cliente** o nel campo **Conto principale per sconti fornitore** per il codice sconto di cassa del cliente o del fornitore indicato nella fattura liquidata.
4.  Il conto principale per gli sconti di cassa, come definito nella pagina **Conti per transazioni automatiche**.

## <a name="example-series-of-cash-discounts"></a>Esempio: Serie di sconti di cassa
Impostare tre codici sconto di cassa come segue:
-   Codice 5G10%: viene applicato uno sconto di cassa del 10% quando l'importo viene pagato entro 5 giorni.
-   Codice 10G5%: viene applicato uno sconto di cassa del 5% quando l'importo viene pagato entro 10 giorni.
-   Codice 14G2%: viene applicato uno sconto di cassa del 2% quando l'importo viene pagato entro 14 giorni.

Nel campo **Codice sconto successivo**:
-   Per il codice 5G10% selezionare 10G5%.
-   Per il codice 10G5% selezionare 14G2%.
-   Per il codice 14D2%, lasciare vuoto il campo Codice sconto successivo.

I tre sconti di cassa si succedono via via che la data del pagamento supera la data dello sconto di cassa precedente sulla fattura. Solo uno sconto di cassa viene concesso quando la fattura viene pagata, in base alla data dello sconto di cassa soddisfatta nella sequenza di sconti di cassa.

## <a name="example-exchange-rates-for-cash-discounts"></a>Esempio: Tassi di cambio per sconti di cassa
La valuta di contabilizzazione della persona giuridica è l'EUR e per gli USD vengono specificati i seguenti tassi di cambio:
-   1 febbraio = 110
-   1 marzo = 80

Una fattura del valore di 1000 USD con termini di sconto di cassa di 20G2% viene registrata il 15 febbraio. L'importo della fattura nella valuta di contabilizzazione è di 1100 EUR. Un pagamento di 980 USD viene liquidato con la fattura il 1 marzo. L'importo dello sconto di cassa è 20 USD. L'importo del pagamento nella valuta di contabilizzazione è di 784 EUR. L'importo dello sconto di cassa nella valuta di contabilizzazione viene calcolato usando il tasso di cambio al 1 marzo: 20 \* 80 / 100 = 16 EUR.

> [!NOTE]
> Se l'opzione **Calcola sconti di cassa per pagamenti parziali** è selezionata in **Parametri di contabilità clienti** o nelle pagine **Parametri di contabilità fornitori**, viene utilizzato il tasso di cambio in vigore alla data di ciascun pagamento parziale. 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
