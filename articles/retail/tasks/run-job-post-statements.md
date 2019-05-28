---
title: Configurare ed eseguire il processo per registrare i rendiconti
description: In questa procedura vengono descritti i passaggi per configurare ed eseguire un processo batch ricorrente al fine di registrare i rendiconti per un punto vendita o un gruppo di punti vendita selezionato.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 676216d90c50c0d3fa1a839cab7a734e624708ba
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1550118"
---
# <a name="configure-and-run-job-to-post-statements"></a>Configurare ed eseguire il processo per registrare i rendiconti

[!include[task guide banner](../includes/task-guide-banner.md)]

In questa procedura vengono descritti i passaggi per configurare ed eseguire un processo batch ricorrente al fine di registrare i rendiconti per un punto vendita o un gruppo di punti vendita selezionato. Questa procedura utilizza i dati dimostrativi della società USRT.

1. Passare a Tutte le aree di lavoro  > Dati finanziari punto vendita al dettaglio.
2. Fare clic su Registra rendiconti.
    * Selezionare una gerarchia organizzativa e quindi nella struttura dei nodi dell'organizzazione, selezionare un punto vendita o un nodo. Selezionare un nodo se si desidera creare il processo batch per un gruppo di punti vendita.  
    * Fare clic sulla freccia per aggiungere la selezione.  
3. Fare clic sulla scheda Esecuzione in background.
4. Selezionare o deselezionare la casella di controllo Elaborazione batch.
5. Fare clic su Ricorrenza.
6. Nel campo Data di inizio, immettere una data.
7. Immettere l'ora nel campo Ora di inizio.
    * Selezionare se si desidera terminare la ricorrenza dopo un numero specifico di cicli, a una data specifica o mai. Quindi scegliere le varie opzioni per definire la frequenza di esecuzione del processo.  
8. Fare clic su OK.
9. Fare clic su OK.

