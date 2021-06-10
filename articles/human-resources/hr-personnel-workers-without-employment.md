---
title: Lavoratori senza impiego
description: I lavoratori senza impiego futuro, attivo o storico con la tua organizzazione compaiono nel modulo Lavoratori senza impiego.
author: andreabichsel
ms.date: 04/06/2021
ms.topic: ''
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorkerV2, HRMMassHireProject, HRMMassHireLine, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2021-04-06
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f6fbada6feb55b8627b1aa1ddfe367177edb7a0a
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6051715"
---
# <a name="workers-without-employment"></a>Lavoratori senza impiego

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

I lavoratori senza impiego futuro, attivo o storico con la tua organizzazione compaiono nel modulo **Lavoratori senza impiego**. I lavoratori con questo stato possono essere visualizzati quando si importano lavoratori senza un record di impiego o quando si elimina l'impiego di un lavoratore tramite **Lavoratori > Storico esperienze lavorative**.

Per impostazione predefinita, il modulo **Lavoratori senza impiego** è disponibile per i seguenti ruoli:

- Assistente risorse umane
- Responsabile risorse umane
- Selezionatore
- Responsabile retribuzioni e benefit
- Amministratore retribuzioni
- Responsabile retribuzioni
- Responsabile formazione

Nell'elenco **Lavoratori senza impiego**, puoi eliminare le persone elencate. Per impostazione predefinita, questo privilegio viene assegnato al ruolo di Assistente risorse umane. Puoi assegnare questo privilegio ad altri ruoli con i seguenti passaggi:

1. Selezionare **Amministrazione sistema** e quindi **Configurazione sicurezza**.

2. Nella scheda **Privilegi**, filtrare l'elenco **Privilegi** in base a **Gestisci lavoratori**.

   [![Filtra l'elenco dei privilegi](./media/hr-personnel-workers-without-employment-filter.png)](./media/hr-personnel-workers-without-employment-filter.png)

3. Nella colonna **Riferimenti**, selezionare colonna, selezionare **Voci di menu Visualizza**.

4. In **Voci di menu Visualizza**, selezionare **HcmWorkersWithoutEmployment**.

   [![Seleziona modulo](./media/hr-personnel-workers-without-employment-select.png)](./media/hr-personnel-workers-without-employment-select.png)

5. Impostare l'autorizzazione **Elimina** su **Concedi**.

6. Selezionare la scheda **Oggetti non pubblicati**.

7. Selezionare **Pubblica tutto**.

   [![Pubblica modifiche](./media/hr-personnel-workers-without-employment-publish.png)](./media/hr-personnel-workers-without-employment-publish.png)

[!INCLUDE[footer-include](../includes/footer-banner.md)]