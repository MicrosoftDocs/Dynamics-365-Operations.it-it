---
title: Introduzione all'ottimizzazione di pianificazione
description: Questo argomento illustra come iniziare a utilizzare la funzionalità di ottimizzazione di pianificazione.
author: ChristianRytt
manager: AnnBe
ms.date: 02/10/2020
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
ms.openlocfilehash: 3e64699005387adcc92e2e7c9fefad68a9de85c0
ms.sourcegitcommit: a688c864fc609e35072ad8fd2c01d71f6a5ee7b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "3076134"
---
# <a name="get-started-with-planning-optimization"></a>Introduzione all'ottimizzazione di pianificazione

[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

La funzionalità di ottimizzazione di pianificazione non supporta attualmente tutte le funzionalità disponibili nel motore di pianificazione incorporato in Microsoft Dynamics 365 Supply Chain Management. Pertanto, è importante valutare se il set di funzionalità attualmente disponibile nell'ottimizzazione di pianificazione soddisfa i requisiti. Per impostazione predefinita, la funzionalità di ottimizzazione di pianificazione non è abilitata in Dynamics Lifecycle Services (LCS). Pertanto, è possibile effettuare la valutazione prima che venga attivata.

Alla fine, l'ottimizzazione di pianificazione sostituirà l'attuale motore di pianificazione integrato Supply Chain Management.

Prima di attivare l'ottimizzazione di pianificazione, si consiglia vivamente di valutare i risultati dell'analisi di adeguatezza dell'ottimizzazione di pianificazione. Per ulteriori informazioni, vedere [Analisi di adeguatezza dell'ottimizzazione di pianificazione](planning-optimization-fit-analysis.md).

### <a name="licensing"></a>Licenze

Se è possibile eseguire la pianificazione generale utilizzando la licenza corrente, non è necessario acquistare una licenza aggiuntiva per iniziare a utilizzare l'ottimizzazione di pianificazione.

### <a name="install-the-add-in"></a>Installare il componente aggiuntivo

Per utilizzare l'ottimizzazione di pianificazione, installare il componente aggiuntivo Ottimizzazione di pianificazione per Dynamics 365 Supply Chain Management. È possibile accedere al componente aggiuntivo dal progetto LCS e attivare la funzionalità di ottimizzazione di pianificazione dall'interfaccia utente (UI) di Supply Chain Management.

> [!NOTE]
> Il requisito per l'ottimizzazione della pianificazione è un ambiente ad alta disponibilità abilitato per LCS (non un ambiente OneBox), con Dynamics 365 Supply Chain Management versione 10.0.7 o successiva.

1. Accedere a LCS e aprire l'ambiente desiderato.
1. Andare a **Dettagli completi**.
1. Scorrere verso il basso fino alla scheda dettaglio **Componenti aggiuntivi dell'ambiente**.
1. Selezionare **Installare un nuovo componente aggiuntivo**.
1. Selezionare **Pianificazione di ottimizzazione**.
1. Seguire la guida all'installazione e accettare le condizioni.
1. Selezionare **Installa**.
1. Nella scheda dettaglio **Componenti aggiuntivi dell'ambiente** dovrebbe essere visualizzato che Ottimizzazione pianificazione è in fase di installazione.
1. Dopo pochi minuti **Installazione in corso** dovrebbe cambiare in **Installato** (è possibile che sia necessario aggiornare la pagina). Una volta installato, è possibile attivare Ottimizzazione pianificazione in Dynamics 365 Supply Chain Management.

### <a name="planning-optimization-integration"></a>Integrazione di ottimizzazione di pianificazione

Per configurare se il componente aggiuntivo Ottimizzazione pianificazione deve essere utilizzato per la pianificazione generale, andare a **Pianificazione generale** \> **Impostazione** \> **Parametri di Ottimizzazione pianificazione**.

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
