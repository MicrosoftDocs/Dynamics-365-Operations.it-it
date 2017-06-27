---
title: Sconti di cassa
description: "Gli sconti di cassa vengono impostati e condivisi per la contabilità fornitori e la contabilità clienti.  Lo sconto di cassa disponibile può essere definito sulla fattura cliente o sulla fattura fornitore e verrà applicato se la fattura viene pagata entro la data dello sconto di cassa."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CashDisc
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3741
ms.assetid: c25f9d85-2702-46aa-8e61-0b4886e069b3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 9d581a1d32a0df15e0b63e129d369d90aaa440d2
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="cash-discounts"></a>Sconti di cassa

[!include[banner](../includes/banner.md)]


Gli sconti di cassa vengono impostati e condivisi per la contabilità fornitori e la contabilità clienti.  Lo sconto di cassa disponibile può essere definito sulla fattura cliente o sulla fattura fornitore e verrà applicato se la fattura viene pagata entro la data dello sconto di cassa. 

<a name="cash-discounts"></a>Sconti di cassa
--------------

Gli sconti di cassa per entrambi i clienti o fornitori possono essere creati nella pagina di sconti di cassa. Utilizzando il campo Codice sconto successivo è inoltre possibile definire una serie di sconti di cassa che si succedono via via che gli sconti di cassa precedenti scadono. Per ulteriori informazioni, vedere "Esempio: Serie di sconti di cassa" più avanti in questo argomento. Se la fattura, la transazione in Avere (un pagamento oppure una nota di accredito) o entrambe sono immesse una valuta diversa da quella di contabilizzazione della persona giuridica, lo sconto di cassa è calcolato usando il tasso di cambio alla data del pagamento o della nota di accredito. Se la fattura e il documento di credito vengono inseriti in persone giuridiche diverse, e se le valute di contabilizzazione per le persone giuridiche differiscono, il tasso di cambio viene preso dalla persona giuridica della fattura, alla data del documento di credito. Per ulteriori informazioni, vedere "Esempio: Tassi di cambio per sconti di cassa" più avanti in questo argomento.
Ordine predefinito del conto principale dello sconto di cassa
----------------------------------------------

Se una fattura viene liquidata in tempo per ottenere uno sconto di cassa, questo verrà registrato automaticamente in un conto principale per sconti di cassa in base alle seguenti priorità di default:
1.  Il conto principale specificato nel campo Conto sconto di cassa alternativo sulla pagina Liquida transazioni aperte del cliente o del fornitore.
2.  Il conto principale specificato nel campo Sconto di cassa cliente o nel campo Sconto di cassa fornitore del gruppo di registrazione contabile assegnato al codice IVA della fattura. Configurare gruppi di registrazione contabile nella pagina Gruppi registrazione contabile e assegnarli ai codici IVA nella relativa pagina.
3.  Il conto di registrazione principale nella pagina Sconti di cassa nel campo Conto principale per sconti cliente o nel campo Conto principale per sconti fornitore per il codice sconto di cassa del cliente o del fornitore indicato nella fattura liquidata.
4.  Il conto principale per gli sconti di cassa, come definito nella pagina Conti per transazioni automatiche.

## <a name="example-series-of-cash-discounts"></a> Esempio: Serie di sconti di cassa
Impostare tre codici sconto di cassa come segue:
-   Codice 5G10%: viene applicato uno sconto di cassa del 10% quando l'importo viene pagato entro 5 giorni.
-   Codice 10G5%: viene applicato uno sconto di cassa del 5% quando l'importo viene pagato entro 10 giorni.
-   Codice 14G2%: viene applicato uno sconto di cassa del 2% quando l'importo viene pagato entro 14 giorni.

Nel campo Codice sconto successivo:
-   Per il codice 5G10% selezionare 10G5%.
-   Per il codice 10G5% selezionare 14G2%.
-   Per il codice 14D2%, lasciare vuoto il campo Codice sconto successivo.

I tre sconti di cassa si succedono via via che la data del pagamento supera la data dello sconto di cassa precedente sulla fattura. Solo uno sconto di cassa viene concesso quando la fattura viene pagata, in base alla data dello sconto di cassa soddisfatta nella sequenza di sconti di cassa.

## <a name="example-exchange-rates-for-cash-discounts"></a> Esempio: Tassi di cambio per sconti di cassa
La valuta di contabilizzazione della persona giuridica è l'EUR e per gli USD vengono specificati i seguenti tassi di cambio:
-   1 febbraio = 110
-   1 marzo = 80

Una fattura del valore di 1000 USD con termini di sconto di cassa di 20G2% viene registrata il 15 febbraio. L'importo della fattura nella valuta di contabilizzazione è di 1100 EUR. Un pagamento di 980 USD viene liquidato con la fattura il 1 marzo. L'importo dello sconto di cassa è 20 USD. L'importo del pagamento nella valuta di contabilizzazione è di 784 EUR. L'importo dello sconto di cassa nella valuta di contabilizzazione viene calcolato usando il tasso di cambio al 1 marzo: 20 \* 80 / 100 = 16 EUR.
| **Nota**                                                                                                                                                                                                                             |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Se l'opzione Calcola sconti di cassa per pagamenti parziali è selezionata nei parametri di contabilità clienti o nelle pagine di parametri di contabilità fornitori, viene utilizzato il tasso di cambio in vigore alla data di ciascun pagamento parziale. |

 
=

 




