---
title: Creare modelli di orario di lavoro
description: I modelli di orario di lavoro definiscono le ore lavorative di una settimana e vengono utilizzati per generare gli orari di lavoro per un periodo di tempo.
author: sorenva
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: OpResLifeCycleManagementWorkspace, WorkTimeTable, WorkTimeCopyDayDialog, WorkPeriodTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8ef913777c8e2aa14af21e28ed56362e31b3d70a1a52e988a90ad94f59b77b70
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6741263"
---
# <a name="create-working-time-templates"></a>Creare modelli di orario di lavoro

[!include [banner](../../includes/banner.md)]

I modelli di orario di lavoro definiscono le ore lavorative di una settimana e vengono utilizzati per generare gli orari di lavoro per un periodo di tempo. Questa procedura consente di definire un modello di orario di lavoro utilizzando le proprietà di programmazione dell'orario di lavoro per classificare gli intervalli di orario di lavoro. È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure utilizzando i propri dati.

1. Andare a **Aree di lavoro > Gestione ciclo di vita risorse**.
1. Selezionare **Modelli di orario di lavoro**

## <a name="create-working-time-template"></a>Creare un modello di orario di lavoro

1. Selezionare **Nuovo**.
1. Nel campo **Modello di orario di lavoro**, immettere un valore.
1. Digitare un valore nel campo **Nome**.
1. Espandere la sezione **Lunedì**.
1. Selezionare **Aggiungi**.
1. Nel campo **Da** immettere un'ora.
    * Specificare l'ora in cui inizia il lavoro di mattina.  
1. Nel campo **A** immettere un'ora.
    * Specificare l'ora in cui i lavoratori iniziano la pausa pranzo.  
1. Selezionare **Aggiungi**.
1. Nel campo **Da** immettere un'ora.
    * Specificare l'ora in cui il lavoro riprende dopo il pranzo.  
1. Nel campo **A** immettere un'ora.
    * Specificare la fine della giornata lavorativa.  

## <a name="replicate-working-times-to-all-week-days"></a>Replicare gli orari di lavoro per tutti i giorni della settimana

1. Seleziona **Copia giorno**.
    * Copiare le definizioni di orario di lavoro da lunedì a martedì.  
1. Selezionare **OK**.
1. Seleziona **Copia giorno**.
    * Copiare le definizioni di orario di lavoro da lunedì a mercoledì.  
1. Selezionare un'opzione nel campo **Al giorno feriale**.
1. Selezionare **OK**.
1. Seleziona **Copia giorno**.
    * Copiare le definizioni di orario di lavoro da lunedì a giovedì.  
1. Selezionare un'opzione nel campo **Al giorno feriale**.
1. Selezionare **OK**.
1. Seleziona **Copia giorno**.
    * Copiare le definizioni di orario di lavoro da lunedì a venerdì.  
1. Selezionare un'opzione nel campo **Al giorno feriale**.
1. Selezionare **OK**.

## <a name="define-time-slots-for-special-operations"></a>Definire le fasce orarie per le operazioni speciali

1. Espandere la sezione **Venerdì**.
1. Nell'elenco trovare e selezionare il record desiderato.
1. Nel campo **Proprietà** immettere o selezionare un valore.
1. Nell'elenco trovare e selezionare il record desiderato.
1. Nel campo **Proprietà** immettere o selezionare un valore.

## <a name="mark-weekend-days-as-closed-for-pickup"></a>Contrassegnare i giorni del fine settimana come chiusi per prelievo

1. Espandere la sezione **Sabato**.
1. Selezionare *Sì* nel campo **Chiuso per prelievo**.
1. Espandere la sezione **Domenica**.
1. Selezionare *Sì* nel campo **Chiuso per prelievo**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]