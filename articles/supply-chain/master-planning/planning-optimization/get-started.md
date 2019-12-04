---
title: Introduzione all'ottimizzazione di pianificazione
description: Questo argomento illustra come iniziare a utilizzare la funzionalità di ottimizzazione di pianificazione.
author: ChristianRytt
manager: AnnBe
ms.date: 10/29/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 37c2acb2397b2a0ad69272c0645bd200a8d7910d
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773987"
---
[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

# <a name="get-started-with-planning-optimization"></a>Introduzione all'ottimizzazione di pianificazione

La funzionalità di ottimizzazione di pianificazione non supporta attualmente tutte le funzionalità disponibili nel motore di pianificazione incorporato in Microsoft Dynamics 365 Supply Chain Management. Pertanto, è importante valutare se il set di funzionalità attualmente disponibile nell'ottimizzazione di pianificazione soddisfa i requisiti. Per impostazione predefinita, la funzionalità di ottimizzazione di pianificazione non è abilitata in Dynamics Lifecycle Services (LCS). Pertanto, è possibile effettuare la valutazione prima che venga attivata.

Alla fine, l'ottimizzazione di pianificazione sostituirà l'attuale motore di pianificazione integrato Supply Chain Management.

Prima di attivare l'ottimizzazione di pianificazione, si consiglia vivamente di valutare i risultati dell'analisi di adeguatezza dell'ottimizzazione di pianificazione. Per ulteriori informazioni, vedere [Analisi di adeguatezza dell'ottimizzazione di pianificazione](planning-optimization-fit-analysis.md).

### <a name="licensing"></a>Licenze

Se è possibile eseguire la pianificazione generale utilizzando la licenza corrente, non è necessario acquistare una licenza aggiuntiva per iniziare a utilizzare l'ottimizzazione di pianificazione.

### <a name="install-the-add-in"></a>Installare il componente aggiuntivo

Per utilizzare l'ottimizzazione di pianificazione, installare il componente aggiuntivo Ottimizzazione di pianificazione per Dynamics 365 Supply Chain Management. È possibile accedere al componente aggiuntivo dal progetto LCS e attivare la funzionalità di ottimizzazione di pianificazione dall'interfaccia utente (UI) di Supply Chain Management.

1. Accedere a LCS e aprire l'ambiente desiderato.
1. Andare a **Dettagli completi**.
1. Selezionare **Gestisci** oppure scorrere verso il basso la scheda dettaglio **Componenti aggiuntivi dell'ambiente**.
1. Selezionare **Installare un nuovo componente aggiuntivo**.
1. Selezionare **Pianificazione di ottimizzazione**.
1. Seguire la guida all'installazione e accettare le condizioni.
1. Selezionare **Installa**.

### <a name="planning-optimization-integration"></a>Integrazione di ottimizzazione di pianificazione

Per configurare se il componente aggiuntivo di ottimizzazione di pianificazione deve essere utilizzato per la pianificazione generale, andare a **Pianificazione generale** \> **Impostazione** \> **Integrazione di ottimizzazione di pianificazione** \> **Parametri di integrazione**.

#### <a name="connection-status"></a>Stato connessione

Lo stato della connessione indica lo stato corrente della connessione tra Supply Chain Management e il servizio di ottimizzazione di pianificazione. Nella seguente tabella vengono illustrati i possibili valori.

| Stato connessione | Descrizione | Può l'ottimizzazione di pianificazione essere utilizzata? |
|---|---|---|
| Connesso | È stata stabilita una connessione tra il servizio di ottimizzazione di pianificazione e Supply Chain Management. | Sì |
| Abilitazione connessione | È attualmente in corso una richiesta di attivazione della connessione al servizio di ottimizzazione di pianificazione. | Nessuno |
| Disconnesso | Non esiste alcuna connessione al servizio di ottimizzazione di pianificazione. La connessione può essere attivata da LCS, come descritto in precedenza in questo argomento. | Nessuno |
| Disabilitazione della connessione | È attualmente in corso una richiesta di disattivazione della connessione al servizio di ottimizzazione di pianificazione. | Nessuno |
| Recupero stato | Il sistema è in attesa delle informazioni sullo stato dal servizio di ottimizzazione di pianificazione. | Nessuno |

#### <a name="the-use-planning-optimization-option"></a>L'opzione Usa ottimizzazione di progettazione

L'impostazione dell'opzione **Usa ottimizzazione di pianificazione** determina il motore di pianificazione utilizzato per la pianificazione generale:

- **Sì** - L'ottimizzazione di pianificazione viene utilizzata per la pianificazione generale.
- **No** - Il motore di pianificazione incorporato Supply Chain Management viene utilizzato per la pianificazione generale.

> [!NOTE]
> Se vengono attivati processi batch di pianificazione esistenti creati per il motore di pianificazione integrato Supply Chain Management mentre l'opzione **Usa ottimizzazione di pianificazione** è impostata su **Sì**, i processi verranno completati.

### <a name="integration-with-the-setup"></a>Integrazione con l'impostazione

Se l'anteprima di ottimizzazione di pianificazione è attivata, la pianificazione generale viene eseguita utilizzando il componente aggiuntivo ottimizzazione di pianificazione. In questo caso, i risultati e le funzionalità della pianificazione generale sono interessati.

## <a name="related-resources"></a>Risorse correlate

[Condizioni per l'anteprima](https://go.microsoft.com/fwlink/?linkid=2015274)

[Panoramica dell'ottimizzazione di pianificazione](planning-optimization-overview.md)

[Analisi di adeguatezza dell'ottimizzazione di pianificazione](planning-optimization-fit-analysis.md)

[Visualizzare la cronologia del piano e i log di pianificazione](plan-history-logs.md)

[Applicare i filtri a un piano](plan-filters.md)

[Annullare un processo di pianificazione](cancel-planning-job.md)
