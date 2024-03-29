---
title: Configurare ed eseguire il processo per registrare i rendiconti
description: In questa procedura vengono descritti i passaggi per configurare ed eseguire un processo batch ricorrente al fine di registrare i rendiconti per un punto vendita o un gruppo di punti vendita selezionato.
author: josaw1
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dfff9e4520659ac1a9d0f85dd0e091f9fa5e2528ff092b650296a47aef9ca7b5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6765858"
---
# <a name="configure-and-run-job-to-post-statements"></a>Configurare ed eseguire il processo per registrare i rendiconti

[!include [banner](../includes/banner.md)]

In questa procedura vengono descritti i passaggi per configurare ed eseguire un processo batch ricorrente al fine di registrare i rendiconti per un punto vendita o un gruppo di punti vendita selezionato. Questa procedura utilizza i dati dimostrativi della società USRT.

1. Passare a Tutte le aree di lavoro  > Dati finanziari punto vendita.
2. Fare clic su Registra rendiconti in batch.
    * Selezionare una gerarchia organizzativa e quindi nella struttura dei nodi dell'organizzazione, selezionare un punto vendita o un nodo. Selezionare un nodo se si desidera creare il processo batch per un gruppo di punti vendita.  
    * Fare clic sulla freccia per aggiungere la selezione.  
3. Fare clic sulla scheda Esecuzione in background. ![Esecuzione in background.](../dev-itpro/media/runbackground.png "Esecuzione in background") 
4. Selezionare o deselezionare la casella di controllo Elaborazione batch.
![Elaborazione batch.](../dev-itpro/media/batchprocessing.png "Elaborazione e ricorrenza batch") 
5. Fare clic su Ricorrenza.
6. Nel campo Data di inizio, immettere una data.
7. Immettere l'ora nel campo Ora di inizio.
    * Selezionare se si desidera terminare la ricorrenza dopo un numero specifico di cicli, a una data specifica o mai. Quindi scegliere le varie opzioni per definire la frequenza di esecuzione del processo.  
8. Fare clic su OK.
9. Fare clic su OK.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]