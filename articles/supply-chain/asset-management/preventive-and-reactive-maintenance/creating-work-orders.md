---
title: Creazione di ordini di lavoro
description: Nell'argomento viene descritto come creare ordini di lavoro in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b23ed3251b2f6cf4f34b423ce2f85301d6ab31a1
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875730"
---
# <a name="creating-work-orders"></a>Creazione di ordini di lavoro


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


Dopo aver programmato processi di manutenzione preventiva, necessario creare ordini di lavoro per i processi. Questa operazione viene eseguita in una dei programmi di manutenzione. I processi programmati in un programma di manutenzione possono avere diversi tipi di riferimenti:

| Tipo di riferimento | Descrizione                    |
|-----------------------|------------------------------------------------------------------------------------------------------------|
| Piani di manutenzione     | Processi di manutenzione preventiva basati su tipi di piani di manutenzione "Tempo" o "Contatore".                       |
| Cicli di manutenzione    | Processi di manutenzione preventiva contenenti vari cespiti che richiedono un tipo di manutenzione simile.           |
| Richiesta di intervento di manutenzione   | Richiesta creata manualmente di manutenzione o riparazione di un cespite, che può essere convertita in un ordine di lavoro. |


1. Fare clic su **Gestione cespiti** > **Comune** > **Tutti i programmi di manutenzione** o **Apri righe di programma di manutenzione** o **Apri pool di programmi di manutenzione**.

2. Selezionare processi di manutenzione programmati per i quali si desidera creare un ordine di lavoro e fare clic su **Ordine di lavoro**. Il numero totale di ore previste per le righe selezionate viene visualizzato nel campo **Ore previste manutenzione**.

3. Nella sezione **Parametri**, selezionare il numero di ordini di lavoro che devono essere creati. È possibile creare un ordine di lavoro per riga di programma di manutenzione, o un numero di ordini di lavoro in base alle selezioni nella sezione **Un ordine di lavoro per**.

4. Selezionare un **tipo di ordine di lavoro** che verrà utilizzato negli ordini di lavoro creati.

5. Fare clic su **OK**. Vengono creati uno o più ordini di lavoro.

![Figura 1](media/18-preventive-maintenance.png)

