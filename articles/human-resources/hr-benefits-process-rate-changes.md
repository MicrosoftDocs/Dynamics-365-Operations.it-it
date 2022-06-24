---
title: Elaborare le modifiche alle tariffe
description: Questo articolo spiega come elaborare le modifiche dei tassi di beneficio in Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitRate, BenefitEligibilityProcessResultViewer
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 09714c70cb00b1a1b5dbd4613bbd70ff11d35cb2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8882955"
---
# <a name="process-rate-changes"></a>Elaborare le modifiche alle tariffe


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo articolo spiega come elaborare le modifiche alle tariffe dei benefici in Microsoft Dynamics 365 Human Resources quando un piano di benefici nuovo o esistente ha un cambiamento nelle impostazioni delle regole di idoneità. Se una nuova regola di idoneità viene creata e assegnata al piano, al sistema viene richiesto di eseguire di nuovo l'idoneità dei lavoratori per verificare se questi ora hanno diritto al piano in base alle nuove opzioni di idoneità. 

1. Nell'area di lavoro **Gestione benefit**, sotto **Elaborazione**, selezionare **Elaborazione aggiornamento modifica tasso**.

2. Nella finestra di dialogo **Esegui elaborazione aggiornamento tasso benefit**, specificare i valori per i seguenti campi:

   | Campo | Descrizione |
   | --- | --- |
   | **Periodo di iscrizione** | Il periodo di iscrizione per il quale elaborare le modifiche al tasso. |

3. Se si desidera eseguire l'elaborazione in background, selezionare **Esecuzione in background** e svolgere le seguenti attività:

   1. Immettere le informazioni per l'elaborazione.

   2. Per impostare un processo ricorrente, selezionare **Ricorrenza**, immettere le informazioni sulla ricorrenza e selezionare **OK**.

   3. Per impostare un avviso di processo, selezionare **Avvisi**, selezionare gli avvisi da ricevere, quindi selezionare **OK**.

   4. Selezionare **OK**. l'elaborazione verrà eseguita con i parametri impostati.

4. Selezionare **OK**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
