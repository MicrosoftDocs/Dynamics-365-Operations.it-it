---
title: Creare una classe di lavoro
description: Questa procedura mostra come impostare una classe di lavoro.
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5def9be0966d65728ffb0897229c0d749e7e13a0
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571795"
---
# <a name="create-a-work-class"></a>Creare una classe di lavoro

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura mostra come impostare una classe di lavoro. Le classi di lavoro vengono utilizzate per indirizzare e/o limitare il tipo di righe ordine di lavoro che un addetto al magazzino può elaborare in un dispositivo mobile. Le righe che un lavoratore può elaborare vengono determinate dalle classi di lavoro sulle voci di menu del dispositivo mobile a cui l'addetto al magazzino può accedere e dalla classe di lavoro specificata nelle righe di lavoro. Le classi di lavoro possono essere utilizzate per convalidare l'ubicazione di stoccaggio per una riga ordine di lavoro. È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure nei propri dati. Questa procedura è destinata al responsabile del magazzino.

1. Andare a Gestione magazzino > Impostazioni > Lavoro > Classi di lavoro.
2. Fare clic su Nuovo.
3. Nel campo ID classe, digitare un valore.
4. Nel campo Descrizione digitare un valore.
5. Nel campo Tipo ordine di lavoro selezionare un'opzione.
6. Fare clic su Nuovo.
7. Digitare un valore nel campo Tipo di ubicazione.
    * Se si seleziona un tipo di ubicazione, viene impostata una restrizione in cui gli articoli possono essere inseriti dopo che sono stati prelevati. Questa impostazione viene utilizzata quando una direttiva ubicazione prova a risolvere l'ubicazione o se un addetto al magazzino fornisce manualmente l'ubicazione per la voce di menu del dispositivo mobile.  
8. Chiudere la pagina.

