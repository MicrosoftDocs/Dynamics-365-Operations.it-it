---
title: Ordini cliente progetto per progetti di tempistica e materiali
description: In questo argomento viene descritto come creare ordini cliente basati su progetti per progetti di tempistica e materiali.
author: KimANelson
manager: AnnBe
ms.date: 04/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2019-04-05
ms.dyn365.ops.version: AX 10.0.2
ms.openlocfilehash: d19ee9de70cd14c78a997b7a87c10b53ab3917b0
ms.sourcegitcommit: ff6dde637d2f5d2bd18a582eb41573d4c69acdd6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2020
ms.locfileid: "3249095"
---
# <a name="project-sales-orders-for-time-and-material-projects"></a>Ordini cliente progetto per progetti di tempistica e materiali

[!include[banner](../includes/banner.md)]

In questo argomento viene descritto come creare un ordine cliente per un progetto. Gli ordini cliente possono essere creati solo per progetti di tipo **tempistica e materiali**.

Se un progetto di tempistica e materiali ha più fonti di finanziamento sul contratto di progetto, è necessario abilitare il parametro **Consenti ordini cliente per progetti con più fonti di finanziamento** nella pagina **Parametri Gestione progetti e contabilità**. 

> [!NOTE]
> - Il supporto per ordini cliente progetto con più fonti di finanziamento è disponibile a partire dalla versione 10.0.2 dell'applicazione.
> - Il parametro per abilitare il supporto per ordini cliente progetto con più fonti di finanziamento verrà rimosso nell'ondata di rilascio di aprile 2020, dopodiché la funzionalità sarà sempre abilitata.

È possibile creare ordini cliente basati su progetti in due modi:

- Accedere al progetto in questione. Nel Riquadro azioni, selezionare **Gestire > Attività articolo > Ordine cliente**. Le informazioni sul progetto passeranno dal progetto all'ordine cliente. Se il contratto di progetto ha più fonti di finanziamento, sarà necessario selezionare la fonte di finanziamento per impostare il cliente per l'ordine cliente. Se è presente una sola fonte di finanziamento per il progetto, il cliente verrà impostato automaticamente.
- Andare alla pagina elenco **Tutti gli ordini cliente** e creare un nuovo ordine cliente. Sarà necessario selezionare il progetto per l'ordine cliente. Dopo la selezione del progetto, il cliente verrà impostato a partire dalla fonte di finanziamento oppure sarà necessario selezionare la fonte di finanziamento se il contratto di progetto ha più fonti di finanziamento.

