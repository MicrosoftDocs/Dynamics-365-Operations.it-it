---
title: Configurare eventi reali futuri
description: Questo articolo descrive come programmare gli eventi della vita futura in Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitFutureLifeEvents, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 183d0f13a17ffac723fac6c4801bd187dd54e976
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8888856"
---
# <a name="configure-future-life-events"></a>Configurare eventi reali futuri

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

È possibile pianificare eventi reali futuri in Dynamics 365 Human Resources.

1. Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Eventi reali futuri**.

2. Selezionare **Nuovo**.

3. Specificare i valori per i seguenti campi:

   | Campo | Descrizione |
   | --- | --- |
   | Data evento reale | Il sistema elabora tutti gli eventi durante il periodo di iscrizione che si verificano fino a questa data. |
   | Evento reale registrato | Data e ora in cui l'evento reale è stato registrato. |
   | Tipo di registro | Indica se l'azione è una delle seguenti:</br></br>- **Aggiorna** - Una modifica a un record esistente che monitora eventi reali</br></br>- **Inserisci** - La creazione di un nuovo record di evento reale |
   | ID tipo di evento reale | Identificatore univoco del tipo di evento reale. |
   | Tipo di evento reale | Catalizzatore per l'aggiornamento dell'iscrizione ai benefit di un dipendente. Per ulteriori dettagli, consultare la sezione Trigger eventi reali. |
   | Stato | Indica se l'evento reale è stato elaborato o meno. |
   | Linea | Numero di riga dell'evento reale futuro. |

4. Selezionare **Salva**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
