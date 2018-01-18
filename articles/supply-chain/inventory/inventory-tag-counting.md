---
title: Conteggio tag scorte
description: Questo articolo fornisce informazioni sul conteggio dei tag, utilizzato per confrontare l'effettivo contenuto di un magazzino con le scorte disponibili.
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventJournalCount, InventJournalCountTag
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, Retail
ms.custom: 11594
ms.assetid: 03772d0e-5c37-454c-ab85-82bc8b60a76d
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 0687058bc76c3ed0dad57b76d54ad57c00987f42
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="inventory-tag-counting"></a>Conteggio tag scorte

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]


Questo articolo fornisce informazioni sul conteggio dei tag, utilizzato per confrontare l'effettivo contenuto di un magazzino con le scorte disponibili.

La creazione di righe nella pagina **Conteggio tag** consente di inserire un numero tag su ogni articolo di magazzino, ad esempio un numero da 1 a 500. Durante il conteggio, si immette il numero di articolo e la quantità su un tag corrispondente. Il tag può quindi essere utilizzato come base per l'inserimento nel giornale di registrazione del conteggio tag. Dopo la registrazione del giornale di registrazione del conteggio tag viene creato un nuovo giornale di registrazione del conteggio nella pagina **Conteggio**. Il nuovo giornale di registrazione si basa sulle righe del giornale di registrazione del conteggio tag creato. Per il conteggio tag degli articoli di una dimensione inventariale specifica selezionare la dimensione nella pagina **Visualizza dimensioni** che appare quando si crea il giornale di registrazione del conteggio tag. Ad esempio, per conteggiare gli articoli in un magazzino specifico, selezionare la casella di controllo **Magazzino**. Se il dispositivo **Blocca articoli durante il conteggio** nella pagina **Parametri di gestione inventario e magazzino** è selezionato, gli articoli non possono essere aggiornati fisicamente durante il conteggio. Tuttavia, gli articoli nei giornali di registrazione del conteggio tag non sono bloccati durante il conteggio. Le operazioni di magazzino non vengono create fino a quando le righe del conteggio tag non vengono registrate e trasferite a un giornale di registrazione. Se i tag vengono immessi casualmente e si desidera visualizzare quelli mancanti, fare clic sull'intestazione della colonna **Tag** per ordinare le righe in base al tag.

<a name="see-also"></a>Vedere anche
--------

[Conteggio ciclo](../warehousing/cycle-counting.md)

