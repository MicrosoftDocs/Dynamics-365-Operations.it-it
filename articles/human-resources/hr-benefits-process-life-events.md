---
title: Elaborare eventi reali
description: Durante il ciclo di vita dei dipendenti in Microsoft Dynamics 365 Human Resources, per ogni dipendente possono verificarsi varie modifiche agli eventi reali.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitLifeEventTypes, BenefitEligibilityProcessResultViewer
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: beac0d6666055a278cab0be9080e49c51885671d
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6057816"
---
# <a name="process-life-events"></a>Elaborare eventi reali

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Durante il ciclo di vita dei dipendenti in Microsoft Dynamics 365 Human Resources, per ogni dipendente possono verificarsi varie modifiche agli eventi reali. Ad esempio, un matrimonio, un cambio di lavoro o un modifica relativa a una persona a carico/beneficiario. Per utilizzare gli eventi reali, è necessario abilitarli nel modulo dei parametri dei benefit, impostare i tipi di eventi reali nonché le opzioni degli eventi reali per i tipi di piano.

Prima di poter elaborare gli eventi reali, è necessario aver già eseguito l'iscrizione aperta almeno una volta durante un periodo di assunzione. Negli Stati Uniti, l'iscrizione aperta è in genere una volta all'anno. Al di fuori degli Stati Uniti, l'iscrizione aperta può essere effettuata al momento dell'assunzione. Un lavoratore non deve selezionare un piano di benefit per poter elaborare eventi reali, ma deve essere stato incluso nell'elaborazione dell'iscrizione aperta. 

Utilizzare l'elaborazione di eventi reali quando vi sono lavoratori con eventi reali che avvengono in una data futura. Questo evento elaborerà tutti gli eventi reali che non sono stati elaborati (come eventi reali futuri o eventi reali che sono stati aggiunti e che non sono specifici a un lavoratore - un esempio è un nuovo benefit). Gli eventi reali in tempo reale sono nascosti.

Ad esempio, se oggi è il 1° febbraio e il 14 febbraio il lavoratore Joe Smith è programmato per cambiare le persone giuridiche, se si esegue l'elaborazione degli eventi reali per il 15 febbraio, il sistema elabora tutti gli eventi fino al 15 febbraio. 

1. Nell'area di lavoro **Gestione benefit**, sotto **Elaborazione**, selezionare **Elaborazione eventi reali**.

2. Nella finestra di dialogo **Esegui elaborazione eventi reali**, specificare i valori per i seguenti campi:

   | Campo | Descrizione |
   | --- | --- |
   | **Periodo di iscrizione** | Il periodo di iscrizione per il quale elaborare gli eventi reali. |
   | **Persona giuridica** | La persona giuridica per la quale elaborare gli eventi reali. |
   | **Data evento reale** | Il sistema elabora tutti gli eventi durante il periodo di iscrizione che si verificano fino a questa data. |
   | **Lavoro** | Il lavoratore per il quale elaborare gli eventi reali. Se questo campo viene lasciato vuoto, gli eventi reali saranno elaborati per tutti i lavoratori. |

3. Se si desidera eseguire l'elaborazione in background, selezionare **Esecuzione in background** e svolgere le seguenti attività:

   1. Immettere le informazioni per l'elaborazione.

   2. Per impostare un processo ricorrente, selezionare **Ricorrenza**, immettere le informazioni sulla ricorrenza e selezionare **OK**.

   3. Per impostare un avviso di processo, selezionare **Avvisi**, selezionare gli avvisi da ricevere, quindi selezionare **OK**.

   4. Selezionare **OK**. l'elaborazione verrà eseguita con i parametri impostati.

4. Selezionare **OK**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]