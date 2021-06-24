---
title: Programmazioni consegna
description: Le programmazioni consegna consentono di tenere traccia della quantità della riga ordine quando si utilizzano più consegne per un singolo ordine cliente, una singola offerta di vendita o un singolo ordine fornitore.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchDeliverySchedule, SalesDeliverySchedule, SalesQuotationDeliverySchedule, SalesQuotationDeliverySchedule
audience: Application User
ms.reviewer: kamaybac
ms.custom: 213984
ms.assetid: 44cac104-c36c-4371-a992-9178b3fd65e9
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3dbd66d499b5d5f9f8ef21c0ce3752031a5f4672
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193784"
---
# <a name="delivery-schedules"></a>Programmazioni consegna

[!include [banner](../includes/banner.md)]

Le programmazioni consegna consentono di tenere traccia della quantità della riga ordine quando si utilizzano più consegne per un singolo ordine cliente, una singola offerta di vendita o un singolo ordine fornitore.

Usare una programmazione consegna quando la quantità totale di una riga ordine o offerta deve essere consegnata in più spedizioni. Le singole spedizioni sono rappresentate dalle righe consegna. Due o più righe consegna formano una programmazione consegna. Le righe consegna possono avere date di consegna, quantità, modalità di consegna e dimensioni di immagazzinamento diverse, ad esempio sito e magazzino.  

**Esempio di una programmazione consegna**

| Articolo                              | Valore                                    |
|-----------------------------------|------------------------------------------|
| Ordine totale (riga ordine originale) | 600 sedie                               |
| Programmazione consegna richiesta       | 100 sedie al mese                     |
| Intervallo temporale di consegna richiesto | 6 mesi, il primo giorno di ogni mese |

In questo scenario il cliente richiede la consegna di 600 sedie in batch di 100 sedie da consegnare in un periodo di sei mesi. Per tenere traccia dei fabbisogni di consegna, si crea una programmazione consegna. Nella pagina di programmazione consegna creare sei righe consegna separate. In ogni riga consegna inserire 100 sedie e indicare la data di consegna di tale lotto. In questo caso ogni riga viene compensata il primo del mese per sei mesi consecutivi.  

Quando si crea una programmazione consegna, il tipo di riga ordine originale viene automaticamente cambiato in **Riga ordine con più consegne**. Una riga di questo tipo viene definita una riga commerciali e viene contrassegnata da un'icona. La riga consegna è contrassegnata da un'icona diversa. Se si modifica una quantità in una riga consegna, la riga commerciale viene aggiornata alla quantità totale della programmazione consegna. Se un accordo commerciale ha definito uno sconto totale per l'ordine, la programmazione consegna assicura che l'ordine sia idoneo per lo sconto sull'ordine totale anche quando l'ordine è diviso in più consegne.  

Gli ordini con una programmazione consegna vengono elaborati a fronte delle righe consegna. L'elaborazione include la registrazione dei documenti di trasporto, delle entrate prodotti e della fatturazione.  

Stampe di documenti di ordini e offerte con una programmazione consegna indicano solo le righe consegna. Non mostrano le righe originali (righe commerciali). **Nota:** inoltre, solo le righe consegna vengono visualizzate quando vengono eseguite le seguenti azioni:

-   Registra
-   Si duplicano pagine
-   Si sfogliano le pagine elenco e i report

Quando si confermano le offerte di vendita, negli ordini clienti risultanti viene visualizzata l'intera programmazione consegna, incluse le righe ordine con più consegne. La programmazione consegna viene visualizzata per intero anche in tutte le pagine principali, ad esempio ordini cliente, offerte di vendita e ordini fornitore.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]