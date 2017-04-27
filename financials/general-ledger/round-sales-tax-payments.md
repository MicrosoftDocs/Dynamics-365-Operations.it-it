---
title: Pagamenti IVA e regole di arrotondamento
description: Questo articolo illustra il funzionamento dell&quot;impostazione della regola di arrotondamento in Uffici IVA e l&quot;arrotondamento del saldo dell&quot;IVA durante il processo Liquida e registra IVA.
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 6134
ms.assetid: 7dcd3cf5-ebdf-4a9f-806c-1296c7da0331
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: ecd32549b6067ed4c1211996e846e210f77f5013
ms.openlocfilehash: 8f28ab4ea0fed975edbed60ddf5630d2d26ba0bc
ms.lasthandoff: 03/31/2017


---

# <a name="sales-tax-payments-and-rounding-rules"></a>Pagamenti IVA e regole di arrotondamento

[!include[banner](../includes/banner.md)]


Questo articolo illustra il funzionamento dell'impostazione della regola di arrotondamento in Uffici IVA e l'arrotondamento del saldo dell'IVA durante il processo Liquida e registra IVA.

Periodicamente, l'IVA deve essere dichiarata e pagata agli uffici tributari. Questa operazione può essere effettuata mediante l'esecuzione del processo di liquidazione e registrazione IVA nella pagina IVA. L'IVA per un periodo verrà liquidata nei conti IVA e il saldo IVA verrà registrato nel conto di liquidazione IVA. Il saldo IVA, registrato nel conto di liquidazione IVA, può essere arrotondato in base a quanto richiesto dagli uffici tributari impostando una regola di arrotondamento nella pagina IVA. 

La differenza di arrotondamento viene registrata nel conto di arrotondamento IVA selezionato nel campo Conti per transazioni automatiche nella contabilità generale.

Nell'esempio seguente viene illustrato il funzionamento della regola di arrotondamento IVA.

### <a name="example"></a>Ad esempio:

L'IVA totale per un periodo mostra un saldo in avere di -98.765,43. La persona giuridica dispone più prelievo IVA superiore a quanto ha pagato. Di conseguenza, la persona giuridica deve denaro all'ufficio tributario. 

La persona giuridica desidera utilizzare un metodo che consenta di arrotondare il saldo all'unità più vicina. L'utente responsabile della contabilità IVA esegue le seguenti operazioni.

1.  Fare clic su Imposta &gt; Imposte indirette &gt; IVA &gt; Uffici IVA.
2.  Nella scheda dettaglio Generale selezionare Normale nel campo Tipo di arrotondamento.
3.  Nel campo Arrotondamento immettere 1.
4.  Al momento del pagamento dell'IVA all'ufficio tributario, aprire la pagina Liquida e registra IVA. Fare clic su Imposta &gt; Dichiarazioni &gt; IVA &gt; Liquida e registra IVA.
5.  Nel conti di liquidazione IVA l'importo di soggettività tributaria di 98.765,43 viene arrotondato a 98.765.

Le seguente tabella mostra un importo di 98.765,43 arrotondato utilizzando ogni metodo di arrotondamento disponibile nel campo Tipo di arrotondamento del modulo Uffici IVA.

| Opzione Tipo di arrotondamento                | Valore arrotondamento = 0,01 | Valore arrotondamento = 0,10 | Valore arrotondamento = 1,00 | Valore arrotondamento = 100,00 |
|-------------------------------------|------------------------|------------------------|------------------------|--------------------------|
| Normale                              | 98.765,43              | 98.765,40              | 98.765,00              | 98.800,00                |
| Arrotondamento per difetto                            | 98.765,43              | 98.765,40              | 98.765,00              | 98.700,00                |
| Arrotondamento per eccesso                         | 98.765,43              | 98.765,50              | 98.766,00              | 98.800,00                |
| A proprio vantaggio, per un saldo in avere | 98.765,43              | 98.765,40              | 98.765,00              | 98.700,00                |
| A proprio vantaggio, per un saldo in dare  | 98.765,43              | 98.765,50              | 98.766,00              | 98.800,00                |

> [!NOTE]                                                                                  
> Se si seleziona A proprio vantaggio, l'arrotondamento è sempre a vantaggio della persona giuridica. 

Per ulteriori informazioni, vedere [Panoramica IVA](indirect-taxes-overview.md). 




