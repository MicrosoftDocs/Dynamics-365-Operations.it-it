---
title: Creare un flusso di lavoro di richieste di acquisto e vendita di congedi
description: Creare un flusso di lavoro di richieste di acquisto e vendita di congedi per acquistare e vendere richieste di congedo in modo coerente in Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-08-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fabe2333bbf76edf31b77c0d5fce044273333de2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8869809"
---
# <a name="create-a-buy-and-sell-leave-request-workflow"></a>Creare un flusso di lavoro di richieste di acquisto e vendita di congedi


>[!Important]
>La funzionalità indicata in questo articolo è attualmente disponibile per i clienti di Dynamics 365 Human Resources standalone. Alcune o tutte le funzionalità saranno disponibili come parte di una versione futura dell'infrastruttura Finance dopo la versione Finance 10.0.26.


[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

È possibile creare un flusso di lavoro in Dynamics 365 Human Resources per gestire richieste di acquisto e vendita di congedi in modo coerente. Un flusso di lavoro **Acquista e vendi congedo** consente di:

- Definire attività
- Determinare chi deve completare le attività
- Specificare chi può approvare o rifiutare le richieste

## <a name="create-a-buy-and-sell-leave-request-workflow"></a>Creare un flusso di lavoro di richieste di acquisto e vendita di congedi

1. Nella pagina **Congedo e assenza**, selezionare la scheda **Collegamenti**.

2. Sotto **Impostazione**, selezionare **Flussi di lavoro risorse umane**.

3. Selezionare **Nuovo**, quindi selezionare **Richiesta di acquisto e vendita di congedi**. 

4. Quando viene visualizzato il messaggio **Aprire questo file?**, selezionare **Apri** e accedi con le credenziali dell'azienda.

5. Utilizzare l'editor di flusso di lavoro per creare un flusso di lavoro per le richieste di congedo. Per ulteriori informazioni sull'uso dei flussi di lavoro, consultare [Panoramica di creazione di flussi di lavoro](../fin-ops-core/fin-ops/organization-administration/create-workflow.md?toc=%2fdynamics365%2fcommerce%2ftoc.json.)

## <a name="leave-and-absence-request-workflow-data-elements"></a>Elementi dati di flusso di lavoro di richieste di congedo e assenza

È possibile utilizzare i seguenti elementi dati per creare approvazioni condizionali o automatiche nei flussi di lavoro per le richieste di acquisto e vendita di congedi:

- **Importo**
- **Criteri di acquisto e vendita congedo**
- **Società**
- **Creato da**
- **Data e ora creazione**
- **Data di fine**
- **Tipo di congedo**
- **Autore modifica**
- **Data e ora modifica**
- **ID richiesta**
- **Data di inizio**
- **Stato** 
- **Data invio**
- **Inviata da**
- **Inviata da Risorse umane**
- **Inviata dal Responsabile**
- **Inviata per conto di**
- **Lavoro**

## <a name="workflow-examples"></a>Esempi di flusso di lavoro

Questi esempi mostrano come è possibile creare diversi tipi di condizioni di flusso di lavoro utilizzando questi elementi dati:

- Utilizzare **Inviata da Risorse umane** e **Inviata dal Responsabile** in un'azione automatica per approvare automaticamente le richieste di acquisto e vendita di congedi inviate da questi ruoli per conto dei dipendenti. Per ulteriori informazioni sulle azioni automatiche, vedere [Configurare i processi di approvazione in un flusso di lavoro](../fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow.md).

- Utilizzare **Tipo di congedo** in un'istruzione condizionale o in un'azione automatica per controllare il modo in cui il flusso di lavoro instrada le richieste con determinati tipi di congedo.

## <a name="see-also"></a>Vedere anche

[Panoramica di congedo e assenza](hr-leave-and-absence-overview.md)<br>
[Gestire i criteri di acquisto e vendita congedo](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)<br>
[Acquista e vendi congedo](hr-employee-self-service-buy-sell-leave.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
