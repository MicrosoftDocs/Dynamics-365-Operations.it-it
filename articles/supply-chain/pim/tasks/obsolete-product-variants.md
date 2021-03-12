---
title: Individuare le varianti prodotto obsolete
description: Questa procedura mostra come trovare prodotti o varianti di prodotto obsoleti e come associare uno stato del ciclo di vita del prodotto ai prodotti obsoleti.
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
ms.openlocfilehash: 2b212a6b4268776893d4e018cab605e6441080fa
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4986856"
---
# <a name="find-obsolete-product-variants"></a>Individuare le varianti prodotto obsolete 

[!include [banner](../../includes/banner.md)]

Questa procedura mostra come trovare prodotti o varianti di prodotto obsoleti e come associare uno stato del ciclo di vita del prodotto ai prodotti obsoleti. Prerequisito: è necessario definire almeno uno stato del ciclo di vita di un prodotto che è inattivo per la progettazione prima di poter eseguire la guida attività.


## <a name="run-a-simulation"></a>Eseguire una simulazione
1. Passare a Gestione delle informazioni sul prodotto > Attività periodiche > Cambia stato del ciclo di vita per prodotti obsoleti.
2. Nel campo Nuovo stato del ciclo di vita prodotto immettere o selezionare un valore.
3. Selezionare Sì nel campo Esegui simulazione senza aggiornare i dati del prodotto.
4. Nel campo Escludi prodotti creati in questo numero di giorni, immettere un numero.
5. Nel campo Escludi prodotti utilizzati nelle transazioni (in numero di giorni), immettere un numero.
6. Espandere la sezione Record da includere.
7. Fare clic su Filtro.
8. Nell'elenco contrassegnare la riga selezionata.
9. Digitare un valore nel campo Criteri.
10. Fare clic su OK.
11. Fare clic su OK.

> [!NOTE]
> Si consiglia di eseguire la simulazione nel batch se si prevede di cercare un numero elevato di prodotti. Inoltre, verificare che la simulazione non venga eseguita durante l'orario di lavoro più attivo della società.  

## <a name="review-the-simulation-results"></a>Esaminare i risultati della simulazione
1. Passare a Gestione delle informazioni sul prodotto > Richieste di informazioni e report > Storico di gestione dello stato del ciclo di vita prodotto.
   
> [!NOTE]
> In questa pagina è possibile esaminare i risultati della simulazione e valutare quanti prodotti e varianti di prodotto saranno associati a un nuovo stato del ciclo di vita del prodotto quando si esegue l'aggiornamento senza simulazione.  

## <a name="run-the-update-of-the-product-lifecycle-state-for-obsolete-products"></a>Eseguire l'aggiornamento dello stato del ciclo di vita per prodotti obsoleti
1. Chiudere la pagina.
2. Passare a Gestione delle informazioni sul prodotto > Attività periodiche > Cambia stato del ciclo di vita per prodotti obsoleti.
3. Espandere la sezione Record da includere.

> [!NOTE]
> Tenere presente che l'ultima selezione è stata salvata.  

4. Selezionare No nel campo Esegui simulazione senza aggiornare i dati del prodotto.
5. Espandere la sezione Esecuzione in background.

> [!NOTE]
> A seconda del numero di prodotti e delle varianti prodotto che vengono modificati, valutare l'opportunità di eseguire il processo in batch. Verificare che non si sta eseguendo un processo di aggiornamento di grandi dimensioni durante le ore lavorative più attive della società.  

6. Fare clic su OK.
7. Passare a Gestione delle informazioni sul prodotto > Richieste di informazioni e report > Storico di gestione dello stato del ciclo di vita prodotto.

> [!NOTE]
> Esaminare i prodotti e le varianti prodotto rilasciati modificati.  

8. Nell'elenco trovare e selezionare il record desiderato.

