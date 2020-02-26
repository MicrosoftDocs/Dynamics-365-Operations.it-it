---
title: Passa tra strutture fornitore
description: In questo argomento viene descritto come passare tra l'integrazione dei dati dei fornitori tra le app Finance and Operations e Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 587a9b98f28b11e303aff4b59e9726f220d956eb
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019853"
---
# <a name="switch-between-vendor-designs"></a>Passa tra strutture fornitore

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

## <a name="vendor-data-flow"></a>Flusso di dati fornitore 

Se si utilizzano altre app di Dynamics 365 per la gestione dei fornitori e si desidera isolare le informazioni sui fornitore quelle sui clienti, utilizzare questa struttura fornitori di base.  

![Flusso di base del fornitore](media/dual-write-vendor-data-flow.png)
 
Se si utilizzano altre app Dynamics 365 per la gestione dei fornitori e si desidera continuare a usare l'entità **Conto** per archiviare le informazioni sui fornitori, utilizzare la nuova struttura fornitori estesa. In questa struttura, le informazioni estese dei fornitori come lo stato in sospeso e il profilo fornitore vengono archiviate nell'entità **fornitori** in Common Data Service. 

![Flusso esteso fornitore](media/dual-write-vendor-detail.jpg)
 
Completare i passaggi di seguito per utilizzare la struttura estesa fornitore: 
 
1. Il pacchetto della soluzione **SupplyChainCommon** contiene i modelli di processo del flusso di lavoro come illustrato nella seguente immagine.
    > [!div class="mx-imgBorder"]
    > ![Modelli del processo del flusso di lavoro](media/dual-write-switch-3.png)
2. Creare nuovi processi del flusso di lavoro utilizzando i modelli del processo del flusso di lavoro: 
    1. Creare un nuovo processo del flusso di lavoro per l'entità **Fornitore** utilizzando il modello di processo del flusso di lavoro **Creare fornitori nell'entità conto** e fare clic su **OK**. Questo flusso di lavoro gestisce lo scenario di creazione del fornitore per l'entità **Conto**.
        > [!div class="mx-imgBorder"]
        > ![Creare fornitori nell'entità conto](media/dual-write-switch-4.png)
    2. Creare un nuovo processo del flusso di lavoro per l'entità **Fornitore** utilizzando il modello di processo del flusso di lavoro **Aggiornare entità conto** e fare clic su **OK**. Questo flusso di lavoro gestisce lo scenario di aggiornamento del fornitore per l'entità **Conto**. 
        > [!div class="mx-imgBorder"]
        > ![Aggiornare entità conto](media/dual-write-switch-5.png)
    3. Creare nuovi processi del flusso di lavoro dai modelli creati sull'entità **Conti**. 
        > [!div class="mx-imgBorder"]
        > ![Creare fornitori nell'entità fornitori](media/dual-write-switch-6.png)
        > [!div class="mx-imgBorder"]
        > ![Aggiornare entità fornitori](media/dual-write-switch-7.png)
    4. È possibile configurare i flussi di lavoro come flussi di lavoro in tempo reale o in background in base ai requisiti. 
        > [!div class="mx-imgBorder"]
        > ![Conversione a un flusso di lavoro in background](media/dual-write-switch-8.png)
    5. Attivare i flussi di lavoro creati sulle entità **Fornitore** e **Account** per iniziare a utilizzare l'entità **Account** per archiviare le informazioni sul fornitore. 
 
