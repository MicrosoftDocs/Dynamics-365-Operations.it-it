---
title: Gestisci ordini pianificati
description: Questo argomento fornisce informazioni sulla modalità di gestione degli ordini pianificati. Viene descritto come aggiornare lo stato degli ordini pianificati, stabilizzarli e filtrare gli ordini pianificati con lo stesso stato dell'ordine pianificato selezionato.
author: roxanadiaconu
manager: AnnBe
ms.date: 09/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19151
ms.assetid: 54123f4c-b4ca-4ce4-9358-b067aa04c968
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ddf2c7b4c67bec6c29387c78d1fdb021d85d702
ms.sourcegitcommit: 620e15555d176eec3905b48d5001af1c50107ce6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2019
ms.locfileid: "1993442"
---
# <a name="maintain-planned-orders"></a>Gestisci ordini pianificati

[!include [banner](../includes/banner.md)]

Questo argomento fornisce informazioni sulla modalità di gestione degli ordini pianificati. Viene descritto come aggiornare lo stato degli ordini pianificati, stabilizzarli e filtrare gli ordini pianificati con lo stesso stato dell'ordine pianificato selezionato.

È possibile gestire gli ordini pianificati nell'area di lavoro **Pianificazione generale**, nell'elenco **Ordine pianificato** o negli elenchi **Ordini di produzione pianificati**, **Ordini fornitore pianificati** e **Trasferimento pianificato**. 

## <a name="planned-order-status"></a>Stato dell'ordine pianificato
È possibile utilizzare il campo **Stato** per tenere facilmente traccia dell'avanzamento. Vengono utilizzati i valori seguenti:

-   Agli ordini pianificati generati mediante la pianificazione generale viene assegnato uno stato di **Inevaso**.
-   A un ordine pianificato che si sceglie di non stabilizzare è possibile assegnare uno stato di **Completato**.
-   Se si desidera stabilizzare un ordine pianificato, è possibile modificare lo stato su **Approvato**. Gli ordini pianificati con stato **Approvato** vengono rispettati dalla pianificazione generale, non vengono modificati né eliminati. 

## <a name="firming-planned-orders"></a>Stabilizzazione degli ordini pianificati 
La stabilizzazione degli ordini pianificati consente di creare gli ordini effettivi. Sono inoltre note come *ordini rilasciati* o *aperti*. Quando un ordine pianificato viene stabilizzato, viene spostato nella sezione relativa agli ordini del modulo rilevante.

È possibile selezionare due opzioni di stabilizzazione dalla pagina **Ordini pianificati**:

-   **Stabilizza** - Questa opzione stabilizza uno o più ordini pianificati selezionati.
-   **Stabilizza tutto** - Questa opzione stabilizza tutti gli ordini pianificati nel filtro. Con **Stabilizza tutto** non è necessario selezionare l'ordine pianificato, tutti gli ordini pianificati nel filtro verranno stabilizzati. Questa opzione può essere utile se stai stabilizzando un numero elevato di ordini pianificati.

> [!NOTE]
> È possibile tenere traccia di un ordine pianificato stabilizzato da **Cronologia stabilizzazione** in **Modulo ordini pianificati > Visualizza > Cronologia stabilizzazione**.

## <a name="parallelize-firming"></a>Stabilizzazione parallela
Se si prevede di stabilizzare più ordini contemporaneamente, parallelizzare l'esecuzione può migliorare il tempo di esecuzione o le prestazioni. Questa opzione è disponibile per stabilizzare più ordini pianificati con **Stabilizza** o **Stabilizza tutto**. Sono disponibili i parametri seguenti:

-   **Stabilizzazione parallela** – Se **Sì**, il processo di stabilizzazione sarà parallelizzato con il numero di thread definiti in **Numero di thread**.
-   **Numero di thread** – Consente di controllare il numero di thread utilizzati per mettere in parallelo il processo di stabilizzazione. Questo parametro viene visualizzato solo se **Stabilizzazione parallela** è impostato su **Sì**.


<a name="additional-resources"></a>Risorse aggiuntive
--------

[Piani generali](master-plans.md)



