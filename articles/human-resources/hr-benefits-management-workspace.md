---
title: Area di lavoro gestione benefit
description: In questo argomento viene descritta l'area di lavoro Gestione benefit in Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 02/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-24
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a2325da54b8d47ef39d0aacb5dac87107ebdd5bf
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019565"
---
# <a name="benefits-management-workspace"></a>Area di lavoro gestione benefit

[!include [applies to](../includes/applies-to-hr.md)]

[!include [preview feature](./includes/preview-feature.md)]

In questo argomento viene descritta l'area di lavoro **Gestione benefit** in Dynamics 365 Human Resources.

> [!NOTE]
> Per visualizzare l'area di lavoro **Gestione benefit**, è necessario dapprima abilitare la funzionalità **(Anteprima) Area di lavoro Gestione benefici** in Gestione funzionalità. Per ulteriori informazioni sull'abilitazione delle funzionalità di anteprima, vedere [Gestire le funzionalità](../hr-admin-manage-features.md).<br><br>![Abilitare l'area di lavoro Gestione benefit](./media/hr-benefits-management-workspace-enable.png)

L'area di lavoro **Gestione benefit** fornisce una rapida visualizzazione dei benefit che richiedono l'attenzione dell'utente. In questa pagina sono visualizzati:

- Totali degli elementi in attesa di azione
- Lavoratori con selezioni non confermate
- Lavoratori che si sono recentemente iscritti a benefit
- Lavoratori con eventi reali futuri
- Nuovi assunti non iscritti
- Lavoratori con eventi reali attivi
- Lavoratori con iscrizioni aperte che non hanno optato per alcun piano

![Area di lavoro gestione benefit](./media/hr-benefits-management-workspace.png)

## <a name="view-action-items"></a>Visualizzare elementi di azione

Puoi visualizzare le tue azioni selezionando un riquadro o una scheda. Se selezioni una scheda, puoi visualizzare e selezionare i lavoratori direttamente nella pagina dell'area di lavoro.

![Elementi di azione](./media/hr-benefits-management-workspace-action-items.png)

Se selezioni un riquadro, vai alla pagina relativa a quell'area. Ad esempio, selezionando uno di questi riquadri, viene visualizzata la pagina **Piani di benefit lavoratori**, filtrata per i dipendenti per i quali è richiesta un'azione:

- **Selezioni non confermate**
- **Iscrizioni aperte senza piani estratti**
- **Iscritto ai benefit**
- **Nuova assunzione senza iscrizione**

![Piani di benefit lavoratore](./media/hr-benefits-management-workspace-plans.png)

La selezione dei riquadri **Eventi reali attivi** o **Eventi reali futuri** comporta la visualizzazione di un elenco di eventi reali attivi o futuri.

![Eventi reali](./media/hr-benefits-management-workspace-life-events.png)

## <a name="processing"></a>In elaborazione

Per elaborare l'idoneità di iscrizione, gli eventi reali o gli aggiornamenti del tasso, selezionare l'elemento appropriato nella barra di navigazione.

![In elaborazione](./media/hr-benefits-management-workspace-processing.png)

Per visualizzare i risultati del processo, selezionare **Risultati processo** nella pagina.

![Risultati processo](./media/hr-benefits-management-workspace-process-results.png)

Per ulteriori informazioni sull'elaborazione dei benefit, vedi:

- [Elaborare l'idoneità di iscrizione](hr-benefits-process-enrollment-eligibility.md)
- [Elaborare le modifiche agli eventi reali](hr-benefits-process-life-event-changes.md)
- [Elaborare l'idoneità degli eventi reali](hr-benefits-process-life-event-eligibility.md)
- [Elaborare gli eventi reali](hr-benefits-process-life-events.md)
- [Elaborare le modifiche alle tariffe](hr-benefits-process-rate-changes.md)

## <a name="change-period"></a>Modifica periodo

Per visualizzare un diverso periodo di benefit, selezionalo nell'elenco a discesa **Periodo**.

![Modifica periodo](./media/hr-benefits-management-workspace-period.png)

## <a name="view-more-options"></a>Visualizzare ulteriori opzioni

Per visualizzare ulteriori informazioni e azioni che puoi eseguire, selezionare **Collegamenti**.

![Collegamenti](./media/hr-benefits-management-workspace-links.png)

## <a name="see-also"></a>Vedere anche

[Panoramica di gestione dei benefit](hr-benefits-management-overview.md)