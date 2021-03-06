---
title: Aggiornare le guide per l'inserimento in Dynamics 365 Talent - Onboard
description: In questo argomento viene descritto come aggiornare le guide per l'inserimento di neoassunti in Microsoft Dynamics 365 Talent - Onboard e come eseguire il push delle modifiche alle guide esistenti.
author: andreabichsel
manager: ''
ms.date: 06/21/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-06-21
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 6175061456a03228043ea13767845cf4b54d6b2e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461685"
---
# <a name="update-onboarding-guides"></a>Aggiornare le guide per l'inserimento

[!include [banner](includes/banner.md)]

Se occorre apportare modifiche alle guide per l'inserimento in Microsoft Dynamics 365 Talent: Onboard, è possibile aggiornarle ed eseguire il push delle modifiche, anche se le guide sono già state inviate. Sono disponibili due opzioni per l'aggiornamento di una guida per l'inserimento:

- Modificare la guida per l'inserimento direttamente e salvare le modifiche.
- Modificare il modello per l'inserimento, eseguire il push delle modifiche in tutte le guide per l'inserimento che sono state create in base al modello.

## <a name="edit-an-onboarding-guide-directly"></a>Modificare guida per l'inserimento direttamente

1. Nel menu a sinistra, selezionare **Guides**.
2. Selezionare la guida che si desidera modificare.
3. Apportare tutte le modifiche desiderate, quindi selezionare **Salva** (simbolo del disco).

    ![[Salvataggio delle modifiche in una guida per l'inserimento](./media/onboard-save.png)](./media/onboard-save.png)

Onboard invierà automaticamente al nuovo assunto un'e-mail che indica quali modifiche sono state apportate. Per una facile identificazione, accanto a ogni modifica sarà visualizzato un tag rosso **Nuova**.

## <a name="update-multiple-guides-by-editing-the-onboarding-template"></a>Aggiornare più guide modificando il modello per l'inserimento

1. Nel menu a sinistra, selezionare **Modelli**.
2. In **modelli personali** selezionare il modello che si desidera modificare.
3. Apportare tutte le modifiche desiderate, quindi selezionare **Salva** (simbolo del disco).
4. Per eseguire il push delle modifiche a tutte le guide basate sul modello, selezionare **Esegui push delle modifiche**.

    ![[Eseguire il push delle modifiche in un modello per l'inserimento a tutte le guide create dal modello](./media/onboard-push-changes.png)](./media/onboard-push-changes.png)

Le modifiche verranno visualizzate nei nuovi assunti che aprono le guide per l'inserimento. Tuttavia, Onboard non avviserà tramite e-mail i nuovi assunti che le guide sono state modificate. Per una facile identificazione, accanto a ogni modifica sarà visualizzato un tag rosso **Nuova**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]