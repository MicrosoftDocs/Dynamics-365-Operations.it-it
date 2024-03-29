---
title: Impostare codici a barre
description: Questo articolo descrive come usare i codici a barre in Dynamics 365 Commerce.
author: josaw1
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.custom: 15971
ms.assetid: 6b4b2ac2-0344-41aa-8818-62c30017d5ac
ms.search.industry: Retail
ms.search.form: RetailBarcodeMaskCharacter, RetailBarcodeMaskSetup
ms.openlocfilehash: 5771ada4a9bba92fb32155ae425f08d6429b46e6
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9271798"
---
# <a name="set-up-bar-codes"></a>Impostare codici a barre

[!include [banner](includes/banner.md)]

Questo articolo descrive come usare i codici a barre in Dynamics 365 Commerce.

È possibile utilizzare i codici a barre per acquistare o vendere prodotti, tenere traccia delle varianti prodotto e impostare clienti e dipendenti. È inoltre possibile utilizzare i codici a barre per emettere e approvare buoni sconto, gift card e note di credito. È possibile impostare prodotti in modo che abbiano codici a barre standard o interni personalizzati. I prodotti possono avere più di un codice a barre. Ad esempio, un prodotto può avere più codici a barre se il prodotto proviene da diversi produttori o se dispone di varianti in base a dimensioni, stile o colore. I codici a barre possono includere il peso o il prezzo del prodotto. Le maschere codice a barre sono modelli utilizzati per creare codici a barre.

> [!NOTE]
> L'assegnazione di un codice a barre univoco a ogni combinazione di varianti consente di eseguire la scansione del codice a barre nel registratore di cassa e individuare automaticamente la variante del prodotto venduta. È anche possibile raccogliere e visualizzare statistiche delle vendite a livello di varianti. A ogni gruppo di dimensioni, colori e stili può essere assegnato un numero univoco che lo identifica nel codice a barre. La maschera codice a barre viene utilizzata da Commerce per generare automaticamente codici a barre per ogni combinazione di varianti. Tale funzionalità può essere utile in presenza di un gran numero di dimensioni, colori e stili poiché le combinazioni aumentano in modo significativo con ogni codice di variante aggiunto. Se non si utilizza questa funzionalità, è necessario assegnare manualmente i codici a barre a ogni combinazione che rappresenta una variante di prodotto.

È possibile creare i codici a barre manualmente o automaticamente. Per creare i codici a barre, completare le seguenti attività nell'ordine in cui sono elencate.

1. [Impostare caratteri di maschera codice a barre](set-up-bar-code-masks.md).
2. [Impostare le maschere codice a barre](set-up-bar-code-masks.md).
3. Configurare le impostazioni dei codici a barre.
4. [Creare codici a barre per prodotti](../supply-chain/pim/tasks/create-bar-code-product.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Impostare le maschere codice a barre](set-up-bar-code-masks.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
