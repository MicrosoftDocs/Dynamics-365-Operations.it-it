---
title: Introduzione alla pianificazione generale
description: Questo articolo illustra come iniziare a utilizzare la funzionalità di pianificazione generale in Dynamics 365 Supply Chain Management.
author: t-benebo
ms.date: 05/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 958de3f9ae6ead6cb6914bd3b7a4560e768013ab
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740331"
---
# <a name="get-started-with-master-planning"></a>Introduzione alla pianificazione generale

[!include [banner](../../includes/banner.md)]

La pianificazione generale in Supply Chain Management è fornita da un servizio esterno chiamato componente aggiuntivo Ottimizzazione pianificazione per Dynamics 365 Supply Chain Management. Questo argomento spiega come ottenere e configurare il servizio.

## <a name="availability"></a>Disponibilità

L'ottimizzazione di pianificazione è attualmente disponibile nelle seguenti aree geografiche di Azure: Stati Uniti, Canada, Brasile, Europa, Francia, Regno Unito, Australia, Asia Pacifico, Giappone e India. Se si tenta di installare il componente aggiuntivo da un'altra area geografica, LCS mostrerà un messaggio che indica che l'area geografica non è supportata. Per ulteriori informazioni sulle aree geografiche di Azure e sulle aree correlate, vedi [Aree geografiche di Azure](https://azure.microsoft.com/global-infrastructure/geographies/#geographies).

L'ottimizzazione di pianificazione non supporta le distribuzioni locali Dynamics 365 Supply Chain Management.

## <a name="licensing"></a>Licenze

Se è possibile eseguire la pianificazione generale utilizzando la licenza corrente, non è necessario acquistare una licenza aggiuntiva per iniziare a utilizzare l'ottimizzazione di pianificazione.

## <a name="install-and-enable-planning-optimization"></a>Installare e abilitare Ottimizzazione pianificazione

Per utilizzare Ottimizzazione pianificazione, è necessario assicurarsi che il sistema disponga di tutti i prerequisiti, quindi abilitare la relativa chiave di licenza e installare il componente aggiuntivo Ottimizzazione pianificazione per Dynamics 365 Supply Chain Management.

### <a name="prerequisites"></a>Prerequisiti

Prima di installare il componente aggiuntivo Ottimizzazione pianificazione, è necessario soddisfare i seguenti prerequisiti:

- È necessario avere Supply Chain Management in esecuzione su un ambiente ad alta disponibilità abilitato per LCS, di livello 2 o maggiore (non un ambiente OneBox), con Dynamics 365 Supply Chain Management versione 10.0.7 o successiva. Se si tenta di installare il componente aggiuntivo in un ambiente OneBox, l'installazione non verrà completata e sarà necessario annullare l'installazione.

- Il tuo sistema deve essere configurato per l'integrazione con Power Platform. Per ulteriori informazioni, vedere [Integrazione di Microsoft Power Platform con le app per la finanza e le operazioni](../../../fin-ops-core/dev-itpro/power-platform/overview.md).

### <a name="enable-the-planning-optimization-license"></a>Abilitare la licenza di Ottimizzazione pianificazione

Per utilizzare Ottimizzazione pianificazione, è necessario abilitare la relativa chiave di configurazione. Fare così:

1. Mettere il sistema in modalità di manutenzione come descritto in [Modalità di manutenzione](../../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Accedere a **Amministrazione sistema \> Imposta \> Configurazione licenza**.
1. Nella scheda **Chiavi di configurazione**, selezionare la casella di controllo per **Ottimizzazione pianificazione**.
1. Disattivare la modalità di manutenzione come descritto in [Modalità di manutenzione](../../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).

### <a name="install-the-planning-optimization-add-in"></a>Installare il componente aggiuntivo Ottimizzazione pianificazione

È necessario installare il componente aggiuntivo dal progetto LCS e attivare la funzionalità di ottimizzazione di pianificazione dall'interfaccia utente di Supply Chain Management.

Per installare il componente aggiuntivo Ottimizzazione pianificazione:

1. Accedere a LCS e aprire l'ambiente desiderato.
1. Andare a **Dettagli completi**.
1. Scorrere verso il basso fino alla scheda dettaglio **Componenti aggiuntivi dell'ambiente**.
1. Selezionare **Installare un nuovo componente aggiuntivo**.
1. Selezionare **Pianificazione di ottimizzazione**.
1. Seguire la guida all'installazione e accettare le condizioni.
1. Seleziona **Installa**.
1. Nella scheda dettaglio **Componenti aggiuntivi dell'ambiente** dovrebbe essere visualizzato che Ottimizzazione pianificazione è in fase di installazione.
1. Dopo pochi minuti **Installazione in corso** dovrebbe cambiare in **Installato** (è possibile che sia necessario aggiornare la pagina). Una volta installato, è possibile attivare Ottimizzazione pianificazione in Dynamics 365 Supply Chain Management.

Lo scopo principale dell'installazione del componente aggiuntivo Ottimizzazione pianificazione è connettere il servizio e l'ambiente. Pertanto, è necessario installare il componente aggiuntivo separatamente su ogni ambiente in cui verrà utilizzato Ottimizzazione pianificazione, indipendentemente da qualsiasi codice spostato tra gli ambienti.

## <a name="integrate-planning-optimization-with-your-system"></a>Integrare Ottimizzazione pianificazione con il tuo sistema

Per configurare se il componente aggiuntivo Ottimizzazione pianificazione deve essere utilizzato per la pianificazione generale, andare a **Pianificazione generale** \> **Impostazione** \> **Parametri di Ottimizzazione pianificazione**.

### <a name="connection-status"></a>Stato connessione

Lo stato della connessione indica lo stato corrente della connessione tra Supply Chain Management e il servizio di ottimizzazione di pianificazione. Nella seguente tabella vengono illustrati i possibili valori.

| Stato connessione | Descrizione | Può l'ottimizzazione di pianificazione essere utilizzata? |
|---|---|---|
| Connesso | È stata stabilita una connessione tra il servizio di ottimizzazione di pianificazione e Supply Chain Management. | Sì |
| Abilitazione connessione | È attualmente in corso una richiesta di attivazione della connessione al servizio di ottimizzazione di pianificazione. | No |
| Disconnesso | Non esiste alcuna connessione al servizio di ottimizzazione di pianificazione. La connessione può essere attivata da LCS, come descritto in precedenza in questo articolo. | Numero |
| Disabilitazione della connessione | È attualmente in corso una richiesta di disattivazione della connessione al servizio di ottimizzazione di pianificazione. | No |
| Recupero stato | Il sistema è in attesa delle informazioni sullo stato dal servizio di ottimizzazione di pianificazione. | No |

### <a name="the-use-planning-optimization-option"></a>L'opzione Usa ottimizzazione di progettazione

L'impostazione dell'opzione **Usa ottimizzazione di pianificazione** determina il motore di pianificazione utilizzato per la pianificazione generale:

- **Sì** - L'ottimizzazione di pianificazione viene utilizzata per la pianificazione generale.
- **No**: il motore di pianificazione generale deprecato viene utilizzato per la pianificazione generale.

Questa impostazione si applica a tutte le persone giuridiche (società). Non è possibile utilizzare Ottimizzazione pianificazione in alcune persone giuridiche e il motore di pianificazione generale deprecato in altre persone giuridiche.

> [!NOTE]
> Se vengono attivati processi batch di pianificazione esistenti creati per il motore di pianificazione generale deprecato mentre l'opzione **Usa ottimizzazione di pianificazione** è impostata su **Sì**, i processi verranno completati.

### <a name="integration-with-the-setup"></a>Integrazione con l'impostazione

Se l'Ottimizzazione pianificazione è attivata, la pianificazione generale viene eseguita utilizzando il componente aggiuntivo ottimizzazione di pianificazione. In questo caso, i risultati e le funzionalità della pianificazione generale sono interessati.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
