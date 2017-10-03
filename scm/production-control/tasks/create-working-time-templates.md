--- 
title: Creare modelli di orario di lavoro
description: I modelli di orario di lavoro definiscono le ore lavorative di una settimana e vengono utilizzati per generare gli orari di lavoro per un periodo di tempo.
author: sorenva
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: ff1978f127a014e75619a4bbbb9b6ff3a3ad7c7a
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---
# <a name="create-working-time-templates"></a>Creare modelli di orario di lavoro

[!include[task guide banner](../../includes/task-guide-banner.md)]

I modelli di orario di lavoro definiscono le ore lavorative di una settimana e vengono utilizzati per generare gli orari di lavoro per un periodo di tempo. Questa procedura consente di definire un modello di orario di lavoro utilizzando le proprietà di programmazione dell'orario di lavoro per classificare gli intervalli di orario di lavoro. È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure utilizzando i propri dati.

1. Andare a Tutte le aree di lavoro > Gestione ciclo di vita risorse.
2. Fare clic su Modelli di orario di lavoro.

## <a name="create-working-time-template"></a>Creare un modello di orario di lavoro
1. Fare clic su Nuovo.
2. Nel campo Modello di orario di lavoro, immettere un valore.
3. Digitare un valore nel campo Nome.
4. Espandere la sezione Lunedì.
5. Scegliere Aggiungi.
6. Nel campo Da immettere un'ora.
    * Specificare l'ora in cui inizia il lavoro di mattina.  
7. Nel campo A immettere un'ora.
    * Specificare l'ora in cui i lavoratori iniziano la pausa pranzo.  
8. Scegliere Aggiungi.
9. Nel campo Da immettere un'ora.
    * Specificare l'ora in cui il lavoro riprende dopo il pranzo.  
10. Nel campo A immettere un'ora.
    * Specificare la fine della giornata lavorativa.  

## <a name="replicate-working-times-to-all-week-days"></a>Replicare gli orari di lavoro per tutti i giorni della settimana
1. Fare clic su Copia giorno.
    * Copiare le definizioni di orario di lavoro da lunedì a martedì.  
2. Fare clic su OK.
3. Fare clic su Copia giorno.
    * Copiare le definizioni di orario di lavoro da lunedì a mercoledì.  
4. Selezionare un'opzione nel campo Al giorno feriale.
5. Fare clic su OK.
6. Fare clic su Copia giorno.
    * Copiare le definizioni di orario di lavoro da lunedì a giovedì.  
7. Selezionare un'opzione nel campo Al giorno feriale.
8. Fare clic su OK.
9. Fare clic su Copia giorno.
    * Copiare le definizioni di orario di lavoro da lunedì a venerdì.  
10. Selezionare un'opzione nel campo Al giorno feriale.
11. Fare clic su OK.

## <a name="define-time-slots-for-special-operations"></a>Definire le fasce orarie per le operazioni speciali
1. Espandere la sezione Venerdì.
2. Nell'elenco trovare e selezionare il record desiderato.
3. Nel campo Proprietà immettere o selezionare un valore.
4. Nell'elenco trovare e selezionare il record desiderato.
5. Nel campo Proprietà immettere o selezionare un valore.

## <a name="mark-weekend-days-as-closed-for-pickup"></a>Contrassegnare i giorni del fine settimana come chiusi per prelievo
1. Espandere la sezione Sabato.
2. Selezionare Sì nel campo Chiuso per prelievo.
3. Espandere la sezione Domenica.
4. Selezionare Sì nel campo Chiuso per prelievo.


