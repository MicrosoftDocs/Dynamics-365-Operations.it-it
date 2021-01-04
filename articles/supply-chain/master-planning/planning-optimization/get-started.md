---
title: Introduzione all'ottimizzazione di pianificazione
description: Questo argomento illustra come iniziare a utilizzare la funzionalità di ottimizzazione di pianificazione.
author: ChristianRytt
manager: tfehr
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 54ad180b7f4691ead3563b077eadadc3b9b20588
ms.sourcegitcommit: 5f21cfde36c43887ec209bba4a12b830a1746fcf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2020
ms.locfileid: "4431594"
---
# <a name="get-started-with-planning-optimization"></a>Introduzione all'ottimizzazione della pianificazione

[!include [banner](../../includes/banner.md)]

Come [annunciato in precedenza](https://docs.microsoft.com/dynamics365/supply-chain/get-started/removed-deprecated-features-scm-updates#use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios), l'ottimizzazione di pianificazione sostituirà il motore di pianificazione generale integrato esistente.

Se attualmente utilizzi il motore di pianificazione generale integrato, dovresti già iniziare a pianificare la migrazione all'ottimizzazione di pianificazione. È importante avviare subito il processo di migrazione perché la deprecazione potrebbe impattare le operazioni. Per evitare problemi dell'ultimo minuto quando viene applicata la deprecazione, ti consigliamo vivamente di completare la migrazione prima del 1° dicembre 2020. 

La funzionalità di ottimizzazione di pianificazione non supporta attualmente tutte le funzionalità disponibili nel motore di pianificazione incorporato in Supply Chain Management. Pertanto, è importante valutare se il set di funzionalità attualmente disponibile nell'ottimizzazione di pianificazione soddisfa i requisiti. La funzionalità di ottimizzazione di pianificazione non è attualmente attivata per impostazione predefinita in Dynamics Lifecycle Services (LCS), quindi hai la possibilità di eseguire una tua valutazione prima che la funzionalità venga attivata.

> [!NOTE]
> Devi richiedere un'eccezione per la migrazione all'ottimizzazione di pianificazione se il processo di pianificazione generale non include la produzione (ordini di produzione pianificati generati tramite la pianificazione generale) e hai bisogno di una versione del motore di pianificazione generale integrato successiva alla versione 10.0.15. A partire dalla versione 10.0.16, verrà visualizzato un errore negli ambienti durante l'esecuzione della pianificazione generale incorporata senza generazione degli ordini di produzione pianificati. L'ottimizzazione di pianificazione deve essere utilizzata per tutte le nuove distribuzioni che non generano ordini di produzione pianificati durante la pianificazione generale. I proprietari di ambienti esistenti che eseguono il motore di pianificazione generale integrato senza la generazione di ordini di produzione pianificati riceveranno una mail con i dettagli sul processo di eccezione. Ti consigliamo di collaborare con un partner per valutare e pianificare la migrazione all'ottimizzazione di pianificazione.

Prima di attivare l'ottimizzazione di pianificazione, si consiglia vivamente di valutare i risultati dell'analisi di adeguatezza dell'ottimizzazione di pianificazione. Per ulteriori informazioni, vedere [Analisi di adeguatezza dell'ottimizzazione di pianificazione](planning-optimization-fit-analysis.md).

### <a name="availability"></a>Disponibilità
L'ottimizzazione di pianificazione è attualmente disponibile nelle seguenti aree geografiche di Azure: Stati Uniti, Canada, Europa, Regno Unito e Australia. Se si tenta di installare il componente aggiuntivo da un'altra area geografica, LCS mostrerà un messaggio che indica che l'area geografica non è supportata.

L'ottimizzazione di pianificazione non supporta le distribuzioni locali Dynamics 365 Supply Chain Management.

### <a name="licensing"></a>Licenze

Se è possibile eseguire la pianificazione generale utilizzando la licenza corrente, non è necessario acquistare una licenza aggiuntiva per iniziare a utilizzare l'ottimizzazione di pianificazione.

### <a name="install-the-add-in"></a>Installare il componente aggiuntivo

Per utilizzare l'ottimizzazione di pianificazione, installare il componente aggiuntivo Ottimizzazione di pianificazione per Dynamics 365 Supply Chain Management. È possibile accedere al componente aggiuntivo dal progetto LCS e attivare la funzionalità di ottimizzazione di pianificazione dall'interfaccia utente (UI) di Supply Chain Management.

> [!NOTE]
> Il requisito per l'ottimizzazione di pianificazione è un ambiente ad alta disponibilità abilitato per LCS, di livello 2 o maggiore (non un ambiente OneBox), con Dynamics 365 Supply Chain Management versione 10.0.7 o successiva. Se si tenta di installare il componente aggiuntivo in un ambiente OneBox, l'installazione non verrà completata e sarà necessario annullare l'installazione.

1. Accedere a LCS e aprire l'ambiente desiderato.
1. Andare a **Dettagli completi**.
1. Scorrere verso il basso fino alla scheda dettaglio **Componenti aggiuntivi dell'ambiente**.
1. Selezionare **Installare un nuovo componente aggiuntivo**.
1. Selezionare **Pianificazione di ottimizzazione**.
1. Seguire la guida all'installazione e accettare le condizioni.
1. Selezionare **Installa**.
1. Nella scheda dettaglio **Componenti aggiuntivi dell'ambiente** dovrebbe essere visualizzato che Ottimizzazione pianificazione è in fase di installazione.
1. Dopo pochi minuti **Installazione in corso** dovrebbe cambiare in **Installato** (è possibile che sia necessario aggiornare la pagina). Una volta installato, è possibile attivare Ottimizzazione pianificazione in Dynamics 365 Supply Chain Management.

Lo scopo principale dell'installazione del componente aggiuntivo Ottimizzazione pianificazione è connettere il servizio e l'ambiente. Pertanto, è necessario installare il componente aggiuntivo separatamente su ogni ambiente in cui verrà utilizzato Ottimizzazione pianificazione, indipendentemente da qualsiasi codice spostato tra gli ambienti.

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

Se l'Ottimizzazione pianificazione è attivata, la pianificazione generale viene eseguita utilizzando il componente aggiuntivo ottimizzazione di pianificazione. In questo caso, i risultati e le funzionalità della pianificazione generale sono interessati.

## <a name="additional-resources"></a>Risorse aggiuntive

[Condizioni per l'anteprima](https://go.microsoft.com/fwlink/?linkid=2015274)

[Panoramica sull'ottimizzazione della pianificazione](planning-optimization-overview.md)

[Analisi di adeguatezza dell'ottimizzazione di pianificazione](planning-optimization-fit-analysis.md)

[Visualizzare la cronologia del piano e i log di pianificazione](plan-history-logs.md)

[Applicare i filtri a un piano](plan-filters.md)

[Annullare un processo di pianificazione](cancel-planning-job.md)
