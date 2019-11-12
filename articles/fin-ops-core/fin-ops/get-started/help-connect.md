---
title: Connettere la Guida
description: In questo argomento vengono descritti i componenti della Guida per le app Finance and Operations e vengono forniti una panoramica della connessione e un riepilogo della creazione della guida personalizzata.
author: margoc
manager: AnnBe
ms.date: 10/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 491024c9c3d6c7d20ef212e167ceab6abac8dac7
ms.sourcegitcommit: d554faca895609b8124bf2ea5aca5a55c407534a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2019
ms.locfileid: "2537857"
---
# <a name="connect-the-help-system"></a>Connettere la Guida

[!include [banner](../includes/banner.md)]

In questo argomento vengono descritti i componenti della Guida per le app Finance and Operations, ad esempio Dynamics 365 Finance, Supply Chain Management, Retail e Talent. Viene fornita una panoramica della procedura per connettere questi componenti e un riepilogo della creazione della Guida personalizzata.

## <a name="help-architecture"></a>Architettura della Guida

La figura seguente mostra le parti della Guida. Nella Guida interna al prodotto vengono visualizzati articoli dal sito all'indirizzo https://docs.microsoft.com e le guide attività archiviate nel Modellatore di processi aziendali in Lifecycle Services (LCS).

> [!NOTE]
> Le funzionalità elencate nel diagramma con un asterisco (\*) sono pianificate, ma non sono ancora disponibili.

[![Architettura della Guida](./media/help-architecture.png)](./media/help-architecture.png)

## <a name="connecting-the-help-system"></a>Connessione della Guida

> [!NOTE]
> La scheda **Guide attività** non è attualmente disponibile in Dynamics 365 Talent o Retail. Attualmente si lavora per abilitare questa funzionalità in una versione successiva. Le Guide attività nell'esperienza Attività iniziali in Talent rimangono disponibili per coprire le funzionalità di base. La Guida sulle procedure è disponibile nel sito docs.microsoft.com per Retail e Talent.

Utilizzando la pagina **Parametri di sistema**, gli amministratori di sistema collegano le parti della Guida per un'implementazione.

[![Modulo Parametri di sistema con impostazioni per la Guida](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)

Nella pagina **Parametri di sistema** effettuare i seguenti passaggi:

> [!IMPORTANT]
> La prima volta che si apre la scheda della **Guida**, è necessario connettersi a Lifecycle Services. Assicurarsi di fare clic sul collegamento al centro del modulo, attendere la connessione, chiudere la finestra di dialogo quindi scegliere **OK** per accedere alla pagina **Parametri di sistema**.
>
> [![Connetti a LCS](./media/connect-to-lcs-crop-1024x365.png "Connetti a LCS")](./media/connect-to-lcs-crop.png)

1. Selezionare il progetto Lifecycle Services a cui connettersi.
2. Selezionare le librerie BPM (nel progetto selezionato) da cui recuperare le registrazioni attività.
3. Impostare l'ordine di visualizzazione delle librerie BPM. Ciò determina l'ordine in cui le registrazioni attività delle librerie verranno visualizzate nel riquadro**Guida**.

Dopo aver completato questi passaggi, è possibile aprire il riquadro **Guida** e fare clic sulla scheda **Guide attività**. Vengono visualizzate le guide attività applicabili alla pagina attualmente aperta nelle app Finance and Operations. Se non viene trovata alcuna guida attività, è possibile immettere le parole chiave per ridefinire la ricerca.

### <a name="showing-translated-task-guides"></a>Visualizzazione delle guide attività tradotte

Le guide attività tradotte sono state fornite per la prima volta nella libreria unificata APQC di maggio 2016 e nella libreria di introduzione. Nelle app Finance and Operations, per visualizzare la Guida attività localizzata, assicurarsi di essere connessi alla libreria di maggio. La lingua in cui viene visualizzata una guida attività è determinata per ogni utente dalle impostazioni di lingua in **Opzioni** &gt; **Preferenze**.

> [!NOTE]
> Anche se molte guide attività sono state tradotte, al momento il client non visualizza i nomi delle guide attività tradotte. Inoltre, solo le guide di attività che sono state rilasciate nel mese di febbraio 2016 sono disponibili in versione tradotta nella libreria di maggio. Si rilascerà una libreria aggiornata con traduzioni aggiuntive.
>
> - Se è stata tradotta una Guida attività, quando si apre la Guida attività tutto il testo apparirà nella lingua selezionata.
> - Se una Guida attività non è stata ancora tradotta, quando si apre solo parte del testo (quello dei controlli) apparirà nella lingua selezionata.

## <a name="creating-custom-help"></a>Creazione di una Guida personalizzata

È possibile utilizzare guide attività per creare una Guida personalizzata oppure collegare un sito Web al riquadro della Guida.

### <a name="create-custom-help-with-task-guides"></a>Creare una Guida personalizzata con guide attività

È possibile creare la Guida personalizzata per Finance, Supply Chain Management e Retail per creare registrazioni attività che riflettono l'implementazione e salvarle in una libreria di processi aziendali LCS. Non è possibile creare Guide attività personalizzate per Talent.

Per i partner, se si promuove una libreria a libreria aziendale e si include in una soluzione, sarà disponibile per i clienti. È inoltre possibile effettuare una copia della libreria globale unificata APQC e quindi aprire la copia, aprire le registrazioni attività dalla copia, modificarle e salvare le registrazioni con le modifiche. Per ulteriori informazioni, vedere [Come creare una registrazione attività da utilizzare come documentazione o formazione](../../dev-itpro/user-interface/task-recorder.md).

### <a name="connect-a-custom-site"></a>Collegare un sito personalizzato

Microsoft ha fornito un white paper e codice di esempio che descrivono come creare e collegare un sito della Guida al riquadro della Guida. Per ulteriori informazioni, vedere:

- [Creazione di una Guida personalizzata per le app Finance and Operations (white paper)](https://go.microsoft.com/fwlink/?linkid=2041185)
- [Archivio GitHub per una Guida personalizzata](https://github.com/microsoft/dynamics356f-o-custom-help)

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della Guida](help-overview.md)

[Panoramica sulla registrazione attività](../../dev-itpro/user-interface/task-recorder.md)

[Come creare una registrazione di attività da utilizzare per documentazione o formazione](../../dev-itpro/user-interface/task-recorder-training-docs.md)