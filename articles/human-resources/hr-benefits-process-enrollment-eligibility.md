---
title: Elaborare l'idoneità di iscrizione
description: In questo articolo viene descritto come eseguire l'elaborazione dell'idoneità di iscrizione.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4dd63e755f0afdbce411b3001410d2e56036e432
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054262"
---
# <a name="process-enrollment-eligibility"></a>Elaborare l'idoneità di iscrizione

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

In questo articolo viene descritto come eseguire l'elaborazione dell'idoneità di iscrizione.

1. Nell'area di lavoro **Gestione benefit**, sotto **Elaborazione**, selezionare **Elaborazione idoneità iscrizione**.

2. Nella finestra di dialogo **Esegui elaborazione idoneità iscrizione a benefit**, specificare i valori per i seguenti campi:

   | Campo | Descrizione |
   | --- | --- |
   | **Periodo di iscrizione** | Il periodo di iscrizione per il quale elaborare l'idoneità di iscrizione. |
   | **Persona giuridica** | La persona giuridica per la quale elaborare l'idoneità di iscrizione. |
   | **Lavoro** | Il lavoratore per il quale elaborare l'idoneità di iscrizione. Se questo campo viene lasciato vuoto, l'idoneità di iscrizione verrà elaborata per tutti i lavoratori. |
   | **Piano benefit** | Il piano di benefit per il quale elaborare l'idoneità di iscrizione.

3. Se si desidera eseguire l'elaborazione in background, selezionare **Esecuzione in background** e svolgere le seguenti attività:

   1. Immettere le informazioni per l'elaborazione.

   2. Per impostare un processo ricorrente, selezionare **Ricorrenza**, immettere le informazioni sulla ricorrenza e selezionare **OK**.

   3. Per impostare un avviso di processo, selezionare **Avvisi**, selezionare gli avvisi da ricevere, quindi selezionare **OK**.

   4. Selezionare **OK**. l'elaborazione verrà eseguita con i parametri impostati.

4. Selezionare **OK**.

## <a name="view-process-results"></a>Visualizzare i risultati del processo

In questo articolo viene descritto come visualizzare i risultati del processo di idoneità.

1.  Nell'area di lavoro **Gestione benefit**, sotto **Elaborazione**, selezionare **Risultati processo**.

2.  Nel modulo **Risultati processo** sono specificati i seguenti campi:

   | Campo | Descrizione |
   | --- | --- |
   | **ID processo** | L'ID univoco per la combinazione di lavoratore, persona giuridica ed esecuzione del processo. |
   | **Tipo di processo** | Identifica il processo che è stato eseguito. Ad esempio: Iscrizione. |
   | **Timbro data/ora** | L'ora in cui è stato eseguito il processo di idoneità. |
   | **Persona giuridica** | La persona giuridica specificata durante il processo di iscrizione. |
   | **Lavoro** | Lavoratore elaborato. |
   | **Piano | Il piano di benefit per cui è stata tentata l'iscrizione. |
   | **Regola di idoneità** | La regola di idoneità che è stata elaborata. Se si è verificato un errore prima dell'esecuzione dell'idoneità, questo campo sarà vuoto. Ad esempio: se non è stato definito un compenso per un lavoratore, il processo di idoneità non verrà eseguito e questo campo verrà lasciato vuoto. |
   | **Stato risultati** | Questo sarà Idoneo o Non idoneo. Lo stato del risultato sarà Non idoneo se il lavoratore non ha soddisfatto i criteri della regola di idoneità, se al lavoratore mancano informazioni richieste come una frequenza di retribuzione o un compenso fisso o se nel piano di benefit mancano informazioni che impediscono ai lavoratori di essere iscritti. |
   | **Messaggio risultati** | Indica perché un lavoratore non è idoneo per un piano di benefit o se è stata approvata la regola di idoneità. |



[!INCLUDE[footer-include](../includes/footer-banner.md)]