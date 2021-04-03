---
title: Impostare un dispositivo per eseguire l'interfaccia di esecuzione dell'area di produzione
description: L'interfaccia di esecuzione dell'area di produzione è configurata per ogni dispositivo dell'area di produzione. Le società in genere configurano ogni dispositivo in modo diverso, a seconda dello scopo che serve. Ad esempio, una società potrebbe avere un dispositivo nell'area della reception, dove i lavoratori entrano ed escono, e un altro nel reparto di produzione, dove i lavoratori gestiscono il lavoro.
author: johanhoffmann
manager: tfehr
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgProductionFloorExecution, HcmWorker, JmgProductionFloorExecutionDeviceConfiguration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 641273dd3ae189853326bf7af7ceb06d48465b5c
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500552"
---
# <a name="set-up-a-device-to-run-the-production-floor-execution-interface"></a>Impostare un dispositivo per eseguire l'interfaccia di esecuzione dell'area di produzione

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

L'interfaccia di esecuzione dell'area di produzione è configurata per ogni dispositivo dell'area di produzione. Le società in genere configurano ogni dispositivo in modo diverso, a seconda dello scopo che serve. Ad esempio, una società potrebbe avere un dispositivo nell'area della reception, dove i lavoratori entrano ed escono, e un altro nel reparto di produzione, dove i lavoratori gestiscono il lavoro.

## <a name="set-the-configuration-and-filters-for-a-specific-device"></a>Impostare la configurazione e i filtri per un dispositivo specifico

Per impostare la configurazione e i filtri dei processi per un dispositivo, accedere alla pagina **Esecuzione area di produzione** utilizzando un account con un ruolo di sicurezza che include il diritto *Supervisore gestione tempo*. (Tra i ruoli di sicurezza predefiniti, solo *Supervisore reparto di produzione* ha questo diritto). Quindi seguire questi passaggi.

1. Aprire il dispositivo che si desidera configurare e accedere a Microsoft Dynamics 365 Supply Chain Management come supervisore del reparto di produzione. (Utilizzare un account che includa il diritto *Supervisore gestione tempo*).
1. Assicurarti che sia disponibile una configurazione per il dispositivo che si sta impostando. Se non esiste già una configurazione, viene fornita una configurazione predefinita. Per ulteriori informazioni su come impostare una configurazione, vedere [Configurare l'interfaccia di esecuzione dell'area di produzione](production-floor-execution-configure.md).
1. Andare a **Controllo produzione \> Esecuzione produzione \> Esecuzione area di produzione**.

    Se l'interfaccia di esecuzione dell'area di produzione è già stata configurata almeno una volta sul dispositivo corrente, viene visualizzata una pagina di accesso. In caso contrario, viene visualizzata una pagina di benvenuto.

1. Nella pagina di accesso o nella pagina di benvenuto, selezionare **Configura**.
1. Selezionare una configurazione nell'elenco.
1. Selezionare **Avanti**.
1. Selezionare uno o più filtri da applicare al dispositivo corrente. Questi filtri aiuteranno a garantire che sul dispositivo vengano visualizzati solo i processi pertinenti. Per impostare un filtro, selezionare il tipo di filtro per aprire un elenco di valori, quindi selezionare il valore in base al quale filtrare. Sono disponibili i filtri seguenti:

    - **Unità di produzione** - Questo è il filtro di livello più alto. Si riferisce in genere a un'ampia area di lavoro che contiene diversi gruppi di risorse e singole risorse.
    - **Gruppo di risorse** - Questo è un filtro di livello medio. In genere si riferisce a una raccolta di risorse correlate in un'area limitata dell'area di lavoro. Se si seleziona prima il filtro **Unità di produzione**, l'elenco dei gruppi di risorse mostra solo i gruppi di quell'unità. In caso contrario, mostra tutti i gruppi di risorse disponibili.
    - **Risorsa** - Questo è il filtro più specifico. Si riferisce in genere a una macchina specifica o un'altra singola risorsa. Se si seleziona prima il filtro **Gruppo di risorse** e/o **Unità di produzione**, l'elenco delle risorse mostra solo le risorse di quel gruppo e/o quell'unità. In caso contrario, mostra tutte le risorse disponibili.

1. Selezionare **OK**.
1. Viene visualizzata la pagina di accesso e il dispositivo è pronto per l'uso.

## <a name="allow-a-worker-to-override-the-default-filters"></a>Consentire a un lavoratore di sostituire i filtri predefiniti

È possibile concedere a lavoratori specifici l'autorizzazione a modificare le impostazioni di filtro su qualsiasi dispositivo utilizzano. Per i lavoratori che dispongono di questa autorizzazione, l'interfaccia di esecuzione dell'area di produzione fornisce un pulsante **Filtro** nelle pagine **Tutti i processi** e **Processo attivo**.

> [!NOTE]
> Se un lavoratore modifica un filtro, il nuovo filtro si applica da quel momento in poi, per tutti gli utenti che accedono al dispositivo.

Per consentire a un lavoratore di sostituire i filtri di processo predefiniti impostati per un dispositivo, seguire questi passaggi.

1. Andare a **Orario e presenze \> Impostazioni \> Lavoratori per registrazione ore**.
1. Selezionare un lavoratore nell'elenco per aprire la pagina **Lavoratori per registrazione ore** di quel lavoratore.
1. Nella scheda **Registrazione ore** impostare l'opzione **Imposta filtri** su *Sì*.

## <a name="run-the-interface-in-full-screen-mode"></a>Eseguire l'interfaccia in modalità a schermo intero

Spesso, si eseguirà l'interfaccia di esecuzione dell'area di produzione su un dispositivo utilizzato esclusivamente a tale scopo. Pertanto, potrebbe avere senso eseguire l'interfaccia in modalità a schermo intero, senza mostrare alcun il riquadro di spostamento e/o browser chrome.

- Per nascondere il riquadro di spostamento visualizzato in Supply Chain Management, aggiungere il testo seguente alla fine dell'URL nella barra degli indirizzi del browser: `\&limitednav=true`.
- Per nascondere anche la barra degli indirizzi del browser, utilizzare la modalità a schermo intero nativa del browser. (Per istruzioni, vedere la documentazione del browser.)

La parte superiore della seguente illustrazione mostra l'aspetto predefinito dell'interfaccia. La parte inferiore mostra come appare in modalità a schermo intero quando il riquadro di spostamento è nascosto.

![Interfaccia standard e a schermo intero](media/pfei-full-screen.png "Interfaccia standard e a schermo intero")

## <a name="extend-the-session-past-12-hours"></a>Estendere la sessione oltre le 12 ore

Per impostazione predefinita, l'interfaccia di esecuzione dell'area di produzione si disconnette automaticamente se nessuno la utilizza per 12 ore. Un utente di Supply Chain Management deve quindi accedere di nuovo. Tuttavia, è possibile estendere il limite di timeout fino a 90 giorni.

Per estendere il limite di timeout, accedere a Supply Chain Management e andare in **Amministrazione di sistema \> Utenti \> Estensioni di sessione**. Specificare l'account utente di Supply Chain Management utilizzato per accedere al dispositivo e il numero di ore per le quali la sessione deve rimanere attiva.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]