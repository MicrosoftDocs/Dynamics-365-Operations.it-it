---
title: Generare un piano con vincoli
description: In questo articolo viene descritta la creazione di un piano in cui verranno considerati sia i vincoli materiali che di capacità.
author: t-benebo
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqPlanSched
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 65884d556724cd6132fe328e95a5bec78885c174
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904016"
---
# <a name="generate-a-constrained-plan"></a>Generare un piano con vincoli

[!include [banner](../../includes/banner.md)]

In questo articolo viene descritta la creazione di un piano in cui verranno considerati sia i vincoli materiali che di capacità. Il piano garantisce che la produzione non inizi prima che i materiali siano disponibili e che le risorse non siano sovraprenotate. 

La società di dati dimostrativi utilizzata per creare questa procedura è USMF. Questa procedura è destinata al responsabile pianificazione produzione.


## <a name="set-up-a-constrained-plan"></a>Impostare un piano con vincoli
1. Nella home page, selezionare l'area di lavoro **Pianificazione generale**.
2. Selezionare **Piani generali** nell'elenco dei collegamenti all'estrema destra dell'area di lavoro.
3. Nell'elenco trovare e selezionare il record desiderato. Esempio: **StaticPlan**  
4. Selezionare **Sì** nel campo **Capacità limitata**.
5. Nel campo **Intervallo temporale capacità limitata** immettere `30`.
6. Espandere la sezione **Intervalli temporali in giorni**.
7. Selezionare **Sì** nel campo **Capacità**.
8. Nel campo **Intervallo temporale programmazione capacità (giorni)** immettere un numero. Esempio: `60`  
9. Selezionare **Sì** nel campo **Ritardi calcolati**.
10. Nel campo **Calcola intervallo temporale dei ritardi (giorni)** immettere un numero. Esempio: `60` 
11. Espandere la sezione **Ritardi calcolati**.
12. Selezionare **Sì** in tutti i campi **Aggiungere il ritardo calcolato alla data del fabbisogno**.
13. Chiudere la pagina.

## <a name="create-a-constrained-plan"></a>Crea un piano con vincoli
1. Selezionare **Esegui**.
2. Nel campo **Piano generale**, immettere o selezionare il piano per cui sono stati impostati dei vincoli.  
3. Selezionare **OK**.
4. Selezionare **Ordini pianificati**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]