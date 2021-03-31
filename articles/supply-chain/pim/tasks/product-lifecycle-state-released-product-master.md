---
title: Assegnare uno stato del ciclo di vita prodotto a una rappresentazione generale prodotto rilasciato
description: In questa procedura viene illustrato come assegnare uno stato del ciclo di vita del prodotto a una rappresentazione generale prodotto rilasciato e alle varianti.
author: cvocph
manager: tfehr
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9a5d7f6532e3c0b61fcc5758f383257d4a9a09b5
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5226739"
---
# <a name="assign-a-product-lifecycle-state-to-a-released-product-master"></a>Assegnare uno stato del ciclo di vita prodotto a una rappresentazione generale prodotto rilasciato

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]