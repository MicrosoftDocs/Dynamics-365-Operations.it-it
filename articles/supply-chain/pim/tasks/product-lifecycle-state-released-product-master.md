--- 
title: Assegnare uno stato del ciclo di vita prodotto a una rappresentazione generale prodotto rilasciato
description: In questa procedura viene illustrato come assegnare uno stato del ciclo di vita del prodotto a una rappresentazione generale prodotto rilasciato e alle varianti.
author: cvocph
manager: AnnBe
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d445ea2f2362f146a1e3e7bcf747898dc2cc89ba
ms.openlocfilehash: f476c1b2585ce0b5b67cd0d91684c86f7d3bda36
ms.contentlocale: it-it
ms.lasthandoff: 02/08/2018

---
# <a name="assign-a-product-lifecycle-state-to-a-released-product-master"></a>Assegnare uno stato del ciclo di vita prodotto a una rappresentazione generale prodotto rilasciato

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

In questa procedura viene illustrato come assegnare uno stato del ciclo di vita del prodotto a una rappresentazione generale prodotto rilasciato e alle varianti. Prerequisito: è necessario esegure la guida di attività "Creare un nuovo stato del ciclo di vita prodotto" per verificare di avere creato almeno uno stato del ciclo di vita del prodotto prima di poter eseguire la guida attività.


## <a name="find-a-released-product-master"></a>Trovare una rappresentazione generale prodotto rilasciata
1. Fare clic su Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati.
2. Nell'elenco trovare e selezionare il record desiderato.

> [!NOTE]
> Una rappresentazione generale prodotto include la rappresentazione generale del prodotto.  

## <a name="update-the-lifecycle-state"></a>Aggiornare lo stato del ciclo di vita
1. Fare clic su Modifica.
2. Nel campo Stato del ciclo di vita prodotto immettere o selezionare un valore.
3. Fare clic su Salva.
4. Fare clic su Sì.

> [!NOTE]
> Se è stato selezionato Sì, tutte le varianti prodotto rilasciate correlati con lo stesso stato originale della rappresentazione generale prodotto rilasciata verranno aggiornate sullo stato del ciclo di vita di prodotti. Se è stato selezionato No, tutte le varianti mantengono lo stato corrente. Le varianti con uno stato del ciclo di vita del prodotto diverso dalla rappresentazione generale prodotto rilasciato non vengono aggiornate.  

## <a name="verify-the-lifecycle-state-of-the-variants"></a>Verificare lo stato del ciclo di vita delle varianti
1. Fare clic su Varianti prodotti rilasciati.

> [!NOTE]
> Tenere presente che tutte le varianti hanno ereditato lo stato selezionato del ciclo di vita della rappresentazione generale prodotto rilasciato.  

2. Nell'elenco contrassegnare la riga selezionata.
3. Nel campo Stato del ciclo di vita prodotto immettere o selezionare un valore.


