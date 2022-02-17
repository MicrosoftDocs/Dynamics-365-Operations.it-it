---
title: Area di lavoro gestione benefit
description: In questo argomento viene descritta l'area di lavoro Gestione benefit in Dynamics 365 Human Resources.
author: twheeloc
ms.date: 01/03/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-24
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 424f4a2098e05b4f7dc6fa84df133dda81cc59f0
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8071464"
---
# <a name="benefits-management-workspace"></a>Area di lavoro gestione benefit


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [applies to](../includes/applies-to-hr.md)]

[!include [preview feature](./includes/preview-feature.md)]

In questo argomento viene descritta l'area di lavoro **Gestione benefit** in Dynamics 365 Human Resources.

> [!NOTE]
> Per visualizzare l'area di lavoro **Gestione benefit**, è necessario dapprima abilitare la funzionalità **(Anteprima) Area di lavoro Gestione benefici** in Gestione funzionalità. Per ulteriori informazioni sull'abilitazione delle funzionalità di anteprima, vedere [Gestire le funzionalità](hr-admin-manage-features.md).<br><br>![Abilitare l'area di lavoro Gestione benefit.](./media/hr-benefits-management-workspace-enable.png)

L'area di lavoro **Gestione benefit** fornisce una rapida visualizzazione dei benefit che richiedono l'attenzione dell'utente. In questa pagina sono visualizzati:

- Totali degli elementi in attesa di azione
- Lavoratori con selezioni non confermate
- Lavoratori che si sono recentemente iscritti a benefit
- Lavoratori con eventi reali futuri
- Nuovi assunti non iscritti
- Lavoratori con eventi reali attivi
- Lavoratori con iscrizioni aperte che non hanno optato per alcun piano

![Area di lavoro gestione benefit.](./media/hr-benefits-management-workspace.png)

## <a name="view-action-items"></a>Visualizzare elementi di azione

È possibile visualizzare le proprie azioni selezionando un riquadro o una scheda. Se si seleziona una scheda, è possibile visualizzare e selezionare i lavoratori dalla pagina dell'area di lavoro.

![Elementi di azione.](./media/hr-benefits-management-workspace-action-items.png)

Se selezioni un riquadro, vai alla pagina relativa a quell'area. Ad esempio, selezionando uno di questi riquadri, viene visualizzata la pagina **Piani di benefit lavoratori**, filtrata per i dipendenti per i quali è richiesta un'azione:

- **Selezioni non confermate**
- **Iscrizioni aperte senza piani estratti**
- **Iscritto ai benefit**
- **Nuova assunzione senza iscrizione**

![Piani di benefit lavoratore.](./media/hr-benefits-management-workspace-plans.png)

La selezione di **Eventi reali attivi** o **Eventi reali futuri** comporta la visualizzazione di un elenco di eventi reali attivi o futuri.

![Eventi reali.](./media/hr-benefits-management-workspace-life-events.png)

## <a name="processing"></a>In elaborazione

Per elaborare l'idoneità di iscrizione, gli eventi reali o gli aggiornamenti del tasso, selezionare l'elemento appropriato nella barra di navigazione.

![In elaborazione.](./media/hr-benefits-management-workspace-processing.png)

Per visualizzare i risultati del processo, selezionare **Risultati processo** nella pagina.

![Risultati processo.](./media/hr-benefits-management-workspace-process-results.png)

Per ulteriori informazioni sull'elaborazione dei benefit, vedi:

- [Elaborare l'idoneità di iscrizione](hr-benefits-process-enrollment-eligibility.md)
- [Elaborare le modifiche agli eventi reali](hr-benefits-process-life-event-changes.md)
- [Elaborare l'idoneità degli eventi reali](hr-benefits-process-life-event-eligibility.md)
- [Elaborare gli eventi reali](hr-benefits-process-life-events.md)
- [Elaborare le modifiche alle tariffe](hr-benefits-process-rate-changes.md)

## <a name="change-period"></a>Modifica periodo

Per visualizzare un diverso periodo di benefit, selezionarlo nell'elenco a discesa **Periodo**.

![Modifica periodo.](./media/hr-benefits-management-workspace-period.png)


## <a name="open-enrollment-tab"></a>Scheda Iscrizione aperta

È possibile visualizzare le proprie azioni selezionando un riquadro o una scheda. Se si seleziona una scheda, è possibile visualizzare e selezionare i lavoratori sulla pagina dell'area di lavoro.
La scheda **Iscrizione aperta** fornisce le metriche chiave per il processo di iscrizione aperta. 

Le informazioni relative all'iscrizione aperta verranno visualizzate 30 giorni prima della **Data di inizio iscrizione**. Questa data è definita nella configurazione **Periodi** in **Gestione benefit** > **Collegamenti** > **Periodi**, nel campo **Data di inizio iscrizione**.  Per modificare questa impostazione, andare a **Parametri condivisi Risorse umane** > **Gestione benefit** > **Opzioni iscrizione aperta** e aggiornare il campo **Numero di**.  

Le seguenti informazioni sono disponibili sulla scheda **Iscrizione aperta**:
 - Dipendenti che non hanno avviato il processo di iscrizione aperta
 - Dipendenti con idoneità in corso
 - Dipendenti con processo di idoneità completato
 - Selezioni non confermate

**Sezioni Riepilogo**

- **Non avviato** - Il riquadro **Non avviato** mostra il numero dei dipendenti che non hanno avviato il processo di iscrizione. Il riquadro **Non avviato** è un elenco filtrato che mostra solo i dipendenti che non hanno alcun piano selezionato, che hanno rinunciato o con piani estratti per il periodo del piano dell'iscrizione aperta. I piani obbligatori vengono ignorati e non sono inclusi perché sono selezionati per impostazione predefinita per il dipendente.  È possibile eseguire il drill-back su questo riquadro per visualizzare un elenco di dipendenti che non hanno avviato il processo di iscrizione aperta sulla pagina **Piano di benefit del lavoratore**.

  > [!NOTE]
  > Se non si desidera monitorare lo stato di avanzamento dell'iscrizione aperta per un **Tipo di piano**, è possibile escluderlo andando a **Gestione benefit** > **Collegamenti** > **Parametri self-service dipendenti** > **Configurazione riquadro piani di benefit** e aggiornando il campo **Monitora stato di avanzamento iscrizione aperta**.  Ad esempio, potrebbero essere presenti piani creati in cui **Tipo di piano** = **Altro**. Questi piani potrebbero essere piani facoltativi per i quali non si desidera monitorare lo stato di avanzamento dell'iscrizione. Se non si seleziona questo tipo di piano, i piani di queste tipologie verranno ignorati durante il monitoraggio dello stato di avanzamento o di completamento dell'iscrizione sulla scheda **Iscrizione aperta**. Questa impostazione si applica al tipo di piano selezionato per tutti i periodi e le persone giuridiche.

- **In corso** - Il riquadro **In corso** fornisce il numero dei dipendenti con idoneità in corso. Il riquadro **In corso** è un elenco filtrato che mostra solo i dipendenti che hanno almeno un piano selezionato e a cui hanno rinunciato. I piani obbligatori vengono ignorati e non sono inclusi perché sono selezionati per impostazione predefinita per il dipendente. È possibile eseguire il drill-back da questo riquadro per visualizzare i piani selezionati e a cui hanno rinunciato sulla pagina **Aggiornamento in blocco dei piani di benefit per lavoratori**.

- **Iscritto ai benefit** - Il riquadro **Iscritto ai benefit** fornisce il,numero dei dipendenti con iscrizione completa ai benefit. Il riquadro **Iscritto ai benefit** è un elenco filtrato che mostra i dipendenti che hanno selezionato o rinunciato a tutti i piani. La query escluderà i piani che non vengono monitorati per l'iscrizione aperta sulla pagina **Parametri self-service dipendenti**. È possibile eseguire il drill-back da questo riquadro per visualizzare un elenco di dipendenti sulla pagina **Piani di benefit lavoratori**.

- **Selezioni non confermate** - Il riquadro **Selezioni non confermate** mostra il numero dei dipendenti che hanno piani selezionati o a cui hanno rinunciato e che devono essere confermati. È possibile eseguire il drill-back da questo riquadro per visualizzare la pagina **Aggiornamento in blocco dei piani di benefit per lavoratori**.

**Attività**

- **Non avviato** - La scheda **Non avviato** mostra un elenco dei dipendenti che non hanno avviato il processo di iscrizione. Il riquadro **Non avviato** è un elenco filtrato che mostra i dipendenti che non hanno alcun piano selezionato, che hanno rinunciato o con piani estratti per il periodo del piano dell'iscrizione aperta. I piani obbligatori vengono ignorati e non sono inclusi perché sono selezionati per impostazione predefinita per il dipendente. È possibile eseguire il drill-down sul lavoratore per visualizzare la pagina **Dettaglio piani di benefit del lavoratore**.

- **Idoneità in corso** - La scheda **Idoneità in corso** mostra un elenco di dipendenti con idoneità in corso. Il riquadro **Idoneità in corso** è un elenco filtrato che mostra i dipendenti che hanno almeno un piano selezionato e a cui hanno rinunciato. I piani obbligatori vengono ignorati e non sono inclusi perché sono selezionati per impostazione predefinita per il dipendente. È possibile eseguire il drill-down sul lavoratore per visualizzare la pagina **Dettaglio piani di benefit del lavoratore**.

## <a name="view-more-options"></a>Visualizzare ulteriori opzioni

Per visualizzare ulteriori informazioni e/o azioni aggiuntive, selezionare **Collegamenti**.

![Collegamenti.](./media/hr-benefits-management-workspace-links.png)

## <a name="see-also"></a>Vedere anche

[Panoramica di gestione dei benefit](hr-benefits-management-overview.md)
