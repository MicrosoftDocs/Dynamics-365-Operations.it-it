---
title: Configurare eventi di vita futuri
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
ms.openlocfilehash: 2cb3ca03e0d9d7e5423a405f1eb0372e1c19588d
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2022
ms.locfileid: "9227987"
---
# <a name="configure-future-life-events"></a>Configurare eventi di vita futuri

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]
[!include [banner](../includes/preview-banner.md)]

È possibile pianificare eventi di vita futuri in Dynamics 365 Human Resources.

1. Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Eventi di vita futuri**.

2. Selezionare **Nuovo**.

3. Specificare i valori per i seguenti campi:

   | Campo | Descrizione |
   | --- | --- |
   | Data evento di vita | Il sistema elabora tutti gli eventi durante il periodo di iscrizione che si verificano fino a questa data. |
   | Evento di vita registrato | Data e ora in cui l'evento di vita è stato registrato. |
   | Tipo di registro | Indica se l'azione è una delle seguenti:</br></br>- **Aggiorna** - Una modifica a un record esistente che monitora eventi di vita</br></br>- **Inserisci** - La creazione di un nuovo record di evento di vita |
   | ID tipo di evento di vita | Identificatore univoco del tipo di evento di vita. |
   | Tipo di evento di vita | Catalizzatore per l'aggiornamento dell'iscrizione ai benefit di un dipendente. Per ulteriori informazioni, consultare la sezione Trigger eventi di vita. |
   | Status | Indica se l'evento di vita è stato elaborato o meno. |
   | Riga | Numero di riga dell'evento di vita futuro. |

4. Seleziona **Salva**. 

È possibile eliminare eventi di vita futuri. Se un evento di vita futuro elaborato viene eliminato, viene eliminato anche il record futuro. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
