---
title: Impostare codici a barre
description: Questo articolo descrive come usare i codici a barre in Microsoft Dynamics 365 for Retail.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15971
ms.assetid: 6b4b2ac2-0344-41aa-8818-62c30017d5ac
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: bfb47e653cc3ef36135fd7c4f60771a354699af7
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="set-up-bar-codes"></a>Impostare codici a barre

[!include[banner](includes/banner.md)]


Questo articolo descrive come usare i codici a barre in Microsoft Dynamics 365 for Retail.

È possibile utilizzare i codici a barre per acquistare o vendere prodotti, tenere traccia delle varianti prodotto e impostare clienti e dipendenti. È inoltre possibile utilizzare i codici a barre per emettere e approvare buoni sconto, gift card e note di credito. È possibile impostare prodotti al dettaglio in modo che abbiano codici a barre standard o interni personalizzati. I prodotti possono avere più di un codice a barre. Ad esempio, un prodotto può avere più codici a barre se il prodotto proviene da diversi produttori o se dispone di varianti in base a dimensioni, stile o colore. I codici a barre possono includere il peso o il prezzo del prodotto. Le maschere codice a barre sono modelli utilizzati per creare codici a barre. **Nota:** l'assegnazione di un codice a barre univoco a ogni combinazione di varianti consente di eseguire la scansione del codice a barre nel registratore di cassa e individuare automaticamente la variante del prodotto venduta. È anche possibile raccogliere e visualizzare statistiche delle vendite a livello di varianti. A ogni gruppo di dimensioni, colori e stili può essere assegnato un numero univoco che lo identifica nel codice a barre. La maschera codice a barre viene utilizzata da Dynamics 365 for Retail per generare automaticamente codici a barre per ogni combinazione di varianti. Tale funzionalità può essere utile in presenza di un gran numero di dimensioni, colori e stili poiché le combinazioni aumentano in modo significativo con ogni codice di variante aggiunto. Se non si utilizza questa funzionalità, è necessario assegnare manualmente i codici a barre a ogni combinazione che rappresenta una variante di prodotto. È possibile creare i codici a barre manualmente o automaticamente. Per creare i codici a barre, completare le seguenti attività nell'ordine in cui sono elencate.

1.  [Impostare caratteri di maschera codice a barre](set-up-bar-code-masks.md).
2.  [Impostare le maschere codice a barre](set-up-bar-code-masks.md).
3.  Configurare le impostazioni dei codici a barre.
4.  Creare codici a barre per prodotti.


<a name="see-also"></a>Vedere anche
--------

[Impostare le maschere codice a barre](set-up-bar-code-masks.md)




