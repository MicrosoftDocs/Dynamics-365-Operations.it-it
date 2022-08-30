---
title: Elaborare le modifiche agli eventi reali
description: Questo articolo spiega come elaborare i cambiamenti degli eventi di vita in Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitLifeEventTypes, BenefitEligibilityProcessResultViewer
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f3d8fbe0270606688944b4465cb5846b8c8f9900
ms.sourcegitcommit: 66d129874635d34a8b29c57762ecf1564e4dc233
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2022
ms.locfileid: "9323504"
---
# <a name="process-life-event-changes"></a>Elaborare le modifiche agli eventi reali

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Elaborare modifiche a eventi reali in Microsoft Dynamics 365 Human Resources per due modifiche a eventi reali:

- Modifiche di compleanno
- Modifiche alle scadenza della sostituzione delle regola di idoneità 

1. Nell'area di lavoro **Gestione benefit**, sotto **Elaborazione**, selezionare **Elaborazione modifica idoneità da eventi reali**.

2. Nella finestra di dialogo **Esegui elaborazione modifica eventi reali**, specificare i valori per i seguenti campi:

   | Campo | Descrizione |
   | --- | --- |
   | Periodo di iscrizione | Il periodo di iscrizione per il quale elaborare le modifiche a eventi reali. |
   | Persona giuridica | La persona giuridica per la quale elaborare le modifiche a eventi reali. |

3. Se si desidera eseguire l'elaborazione in background, selezionare **Esecuzione in background** e svolgere le seguenti attività:

   1. Immettere le informazioni per l'elaborazione.

   2. Per impostare un processo ricorrente, selezionare **Ricorrenza**, immettere le informazioni sulla ricorrenza e selezionare **OK**.

   3. Per impostare un avviso di processo, selezionare **Avvisi**, selezionare gli avvisi da ricevere, quindi selezionare **OK**.

   4. Selezionare **OK**. l'elaborazione verrà eseguita con i parametri impostati.

4. Selezionare **OK**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
