--- 
title: Generare un piano con vincoli
description: "In questa procedura viene descritta la creazione di un piano in cui verranno considerati sia i vincoli materiali che di capacità."
author: ShylaThompson
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 59c6a4a2b239b3fd6b6ddc8f06bfd007f0191f0a
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="generate-a-constrained-plan"></a>Generare un piano con vincoli

[!include [task guide banner](../../includes/task-guide-banner.md)]

In questa procedura viene descritta la creazione di un piano in cui verranno considerati sia i vincoli materiali che di capacità. Il piano garantisce che la produzione non inizi prima che i materiali siano disponibili e che le risorse non siano sovraprenotate. 

La società di dati dimostrativi utilizzata per creare questa procedura è USMF. Questa procedura è destinata al responsabile pianificazione produzione.


## <a name="set-up-a-constrained-plan"></a>Impostare un piano con vincoli
1. Fare clic su Pianificazione generale.
2. Fare clic su Piani generali.
3. Nell'elenco trovare e selezionare il record desiderato.
    * Esempio: StaticPlan  
4. Selezionare Sì nel campo Capacità limitata.
5. Nel campo Intervallo temporale capacità limitata immettere "30".
6. Espandere gli intervalli temporali nella sezione Giorni.
7. Selezionare Sì nel campo Capacità.
8. Nel campo Intervallo temporale programmazione capacità (giorni) immettere un numero.
    * Esempio: 60  
9. Selezionare Sì nel campo Ritardi calcolati.
10. Nel campo Calcola intervallo temporale dei ritardi (giorni) immettere un numero.
    * Esempio: 60  
11. Espandere la sezione Ritardi calcolati.
12. Selezionare Sì nel campo Aggiungere il ritardo calcolato alla data del fabbisogno
13. Selezionare Sì nel campo Aggiungere il ritardo calcolato alla data del fabbisogno
14. Selezionare Sì nel campo Aggiungere il ritardo calcolato alla data del fabbisogno
15. Chiudere la pagina.

## <a name="create-a-constrained-plan"></a>Crea un piano con vincoli
1. Fare clic su Esegui.
2. Nel campo Piano generale immettere o selezionare un valore.
    * Selezionare il piano per cui sono stati impostati i vincoli.  
3. Fare clic su OK.
    * Questa operazione potrebbe richiedere tempo.  
4. Fare clic su Ordini pianificati.


