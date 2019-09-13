---
title: Aggiungere registrazioni di errore all'ordine di lavoro
description: In questo argomento viene descritto come aggiungere registrazioni di errore agli ordini di lavoro in Gestione cespiti.
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
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7c86973ca44d9113d14e180e27cc51343da5d2c0
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875740"
---
# <a name="add-fault-to-work-order"></a>Aggiungere registrazioni di errore all'ordine di lavoro

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


È possibile aggiungere registrazioni di errore impostate in Designer errori a un ordine di lavoro. Il cespite selezionato nell'ordine di lavoro deve contenere tipi di cespite che hanno uno o più record di errore ad esso collegati. Per ulteriori informazioni, leggere la sezione [Gestione errori](../setup-for-work-orders/fault-management.md).

1. Fare clic su **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.

2. Nell'elenco, selezionare l'ordine di lavoro in cui si desidera effettuare una registrazione di errore e fare clic su **Errore di cespite**.

3. Nella Scheda dettaglio **Sintomi** fare clic su **Aggiungi riga**. Un numero di errore sequenziale viene automaticamente inserito nel campo **Errore**.

4. Selezionare il sintomo pertinente nel campo **Sintomo errore**.

5. Selezionare **Area di errore** e **Tipo di errore**.

6. La data corrente viene inserita automaticamente nel campo **Data errore**. Se necessario, è possibile selezionare un'altra data.

7. Nella Scheda dettaglio **Cause del sintomo selezionato**, aggiungere una riga che descrive la causa del problema.

8. Nella Scheda dettaglio **Rimedi per sintomo selezionato**, aggiungere una riga che descrive una possibile soluzione per il problema.

9. Fare clic su **Salva**.

![Figura 1](media/19-work-orders.png)


## <a name="view-asset-faults"></a>Visualizzare gli errori registrati nei cespiti

Nell'elenco **Errori di cespite**, è possibile ottenere una panoramica di tutti gli errori registrati nei cespiti.

Fare clic su **Gestione cespiti** > **Richieste di informazioni** > **Errore di cespite** > **Errori di cespite** per aprire l'elenco.


## <a name="print-asset-fault-report"></a>Stampare il report degli errori di cespite

Nella pagina elenco **Tutti i cespiti**, è possibile stampare un report degli errori di cespite contenente tutte le registrazioni di errore nonché una panoramica grafica delle statistiche degli errori.

1. Fare clic su **Gestione cespiti** > **Comune** > **Cespiti** > **Tutti i cespiti**.

2. Nell'elenco **Cespiti**, selezionare il cespite per il quale si desidera stampare un report degli errori.

3. Nella scheda **Generale** > **Sezione report**, fare clic su **Errore di cespite**.

4. Inserire un periodo specifico oppure selezionare un tipo di errore.

5. Fare clic su **OK** per stampare il report.

>[!NOTE]
>È inoltre possibile stampare un report degli errori per vari cespiti o tipi di cespite facendo clic su **Gestione cespiti** > **Report** > **Cespiti** > **Errore di cespite**.

