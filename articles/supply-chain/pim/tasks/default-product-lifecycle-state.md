--- 
title: Creare uno stato predefinito del ciclo di vita del prodotto
description: "In questa procedura viene illustrato come creare uno stato del ciclo di vita del prodotto predefinito nonché come associare lo stato predefinito con i prodotti rilasciati."
author: cvocph
manager: AnnBe
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d445ea2f2362f146a1e3e7bcf747898dc2cc89ba
ms.openlocfilehash: 06a6c7c8fa767edf6fdf50c3c971b6d767f8755f
ms.contentlocale: it-it
ms.lasthandoff: 02/08/2018

---
# <a name="create-a-default-product-lifecycle-state"></a>Creare uno stato predefinito del ciclo di vita del prodotto

[!include [task guide banner](../../includes/task-guide-banner.md)]

In questa procedura viene illustrato come creare uno stato del ciclo di vita del prodotto predefinito nonché come associare lo stato predefinito con i prodotti rilasciati.


## <a name="create-a-default-lifecycle-state"></a>Creare uno stato predefinito del ciclo di vita
1. Fare clic su Gestione informazioni sul prodotto > Impostazioni > Stato del ciclo di vita prodotto.
2. Fare clic su Nuovo.
3. Nel campo Stato digitare un valore.
4. Selezionare Sì nel campo Impostazione predefinita quando rilasciato a persona giuridica.
5. Nel campo Descrizione digitare un valore.
6. Selezionare No nel campo Attivo per pianificazione.

> [!NOTE]
> Se un nuovo prodotto rilasciato non deve essere incluso nella pianificazione generale, selezionare No. Se deve essere incluso nella pianificazione generale, lasciare il controllo sul valore predefinito Sì.  

## <a name="create-a-new-released-product"></a>Creare un nuovo prodotto rilasciato
1. Chiudere la pagina.
2. Fare clic su Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati.
3. Fare clic su Nuovo.
4. Nel campo Numero prodotto, digitare un valore.
5. Digitare un valore nel campo Nome prodotto.
6. Digitare un valore nel campo Nome di ricerca.
7. Nel campo Gruppo modello articolo immettere o selezionare un valore.
8. Nel campo Gruppo di articoli immettere o selezionare un valore.
9. Nel campo Dimensione di immagazzinamento immettere o selezionare un valore.
10. Nel campo Dimensione di tracciabilità immettere o selezionare un valore.
11. Fare clic su OK.

> [!NOTE]
> Lo stato del ciclo di vita del prodotto predefinito è una definizione globale.  

## <a name="change-the-product-to-an-active-state"></a>Modificare il prodotto su uno stato attivo
1. Nel campo Stato del ciclo di vita prodotto immettere o selezionare un valore.

> [!NOTE]
> Si supponga di aver impostato uno stato attivo, è possibile ora selezionare lo stato attivo per consentire al prodotto di essere utilizzato nel calcolo del livello DBA e della pianificazione generale. Ovviamente, ciò è applicabile solo se tutti i dettagli prodotto necessari per una pianificazione coerente vengono specificati.  


