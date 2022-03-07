---
title: Elaborare modifiche ai tassi
description: Elaborare modifiche ai tassi di benefit in Microsoft Dynamics 365 Human Resources quando un piano di benefit nuovo o esistente presenta una modifica nelle impostazioni della regola di idoneità.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitRate, BenefitEligibilityProcessResultViewer
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c841f5d5d409c7e73cdc38988f8233747a11f837
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5803827"
---
# <a name="process-rate-changes"></a>Elaborare modifiche ai tassi

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Elaborare modifiche ai tassi di benefit in Microsoft Dynamics 365 Human Resources quando un piano di benefit nuovo o esistente presenta una modifica nelle impostazioni della regola di idoneità. Se una nuova regola di idoneità viene creata e assegnata al piano, al sistema viene richiesto di eseguire di nuovo l'idoneità dei lavoratori per verificare se questi ora hanno diritto al piano in base alle nuove opzioni di idoneità. 

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