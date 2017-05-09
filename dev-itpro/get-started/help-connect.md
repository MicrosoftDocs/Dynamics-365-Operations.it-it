---
title: Collegamento alla Guida
description: In questo argomento vengono descritti i componenti della Guida per Microsoft Dynamics 365 for Operations e vengono forniti una panoramica della connessione e un riepilogo della creazione della guida personalizzata.
author: margoc
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: 5ac5e30cff2239f601778001368fa7aaba478f5c
ms.lasthandoff: 03/31/2017


---

# <a name="connect-the-help-system"></a>Collegamento alla Guida

Vengono descritti i componenti della Guida di Microsoft Dynamics 365 for Operations. Viene fornita una panoramica della procedura per connettere questi componenti e un riepilogo della creazione della Guida personalizzata. 

<a name="help-architecture"></a>Architettura della Guida
-----------------

La figura seguente mostra le parti della Guida di Dynamics 365 for Operations. Nella Guida interna al prodotto vengono visualizzati articoli dal sito di Dynamics 365 for Operations all'indirizzo https://docs.microsoft.com e le guide attività archiviate nel Modellatore di processi aziendali in Lifecycle Services (LCS). 
**Nota:** Le funzionalità elencate nel diagramma con un asterisco  (\*) sono pianificate, ma non sono ancora disponibili. [![Architettura della Guida](./media/help-architecture.png)](./media/help-architecture.png)

## <a name="connecting-the-help-system"></a>Connessione della Guida
Utilizzando la pagina **Parametri di sistema**, gli amministratori di sistema collegano le parti della Guida per un'implementazione. [![Modulo Parametri di sistema con impostazioni della Guida](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png) Nella pagina **Parametri di sistema **effettuare le operazioni seguenti:

1.  **Importante**: La prima volta che si apre la scheda **Guida**, è necessario connettersi a Lifecycle Services. Assicurarsi di fare clic sul collegamento al centro del modulo, attendere la connessione, chiudere la finestra di dialogo quindi scegliere **OK** per ottenere la pagina **Parametri di sistema**.[![Connetti a LCS](./media/connect-to-lcs-crop-1024x365.png "Connetti a LCS")](./media/connect-to-lcs-crop.png)
2.  Selezionare il progetto Lifecycle Services a cui connettersi.
3.  Selezionare le librerie BPM (nel progetto selezionato) da cui recuperare le registrazioni attività.
4.  Impostare l'ordine di visualizzazione delle librerie BPM. Ciò determina l'ordine in cui le registrazioni attività delle librerie verranno visualizzate nel riquadro**Guida**.

Dopo il completamento di questi passaggi, è possibile aprire il riquadro **Guida** e fare clic sulla scheda **Guide attività**. Saranno ora visualizzate le guide attività applicabili alla pagina attualmente aperta in Dynamics 365 for Operations. Se non viene trovata alcuna guida attività, è possibile immettere le parole chiave per ridefinire la ricerca.

### <a name="showing-translated-task-guides"></a>Visualizzazione delle guide attività tradotte

Le guide attività tradotte sono state fornite per la prima volta nella libreria unificata APQC di maggio 2016 e nella libreria di introduzione. In Dynamics 365 for Operations, per visualizzare la guida attività localizzata, assicurarsi di essere connessi alla libreria di maggio. La lingua in cui viene visualizzata una guida attività è determinata per ogni utente dalle impostazioni di lingua in **Opzioni** &gt; **Preferenze**. **Nota:** anche se molte guide attività sono state tradotte, al momento il client Dynamics 365 for Operations non visualizza i nomi delle guide attività tradotte. Inoltre, solo le guide di attività che sono state rilasciate nel mese di febbraio 2016 sono disponibili in versione tradotta nella libreria di maggio. Si rilascerà una libreria aggiornata con traduzioni aggiuntive.

-   Se è stata tradotta una Guida attività, quando si apre la Guida attività tutto il testo apparirà nella lingua selezionata.
-   Se una Guida attività non è stata ancora tradotta, quando si apre solo parte del testo (quello dei controlli) apparirà nella lingua selezionata.

## <a name="creating-custom-help"></a>Creazione di una Guida personalizzata
È possibile creare la Guida personalizzata per l'implementazione di Dynamics 365 for Operations per creare registrazioni attività che riflettono l'implementazione e salvarle in una libreria di processi aziendali LCS. Per i partner, se si promuove una libreria a libreria aziendale e si include in una soluzione, sarà disponibile per i clienti. È inoltre possibile effettuare una copia della libreria globale unificata APQC e quindi aprire la copia, aprire le registrazioni attività dalla copia, modificarle e salvare le registrazioni con le modifiche. Per ulteriori informazioni, vedere [Come creare una registrazione attività da utilizzare come documentazione o formazione](../user-interface/task-recorder.md).

<a name="see-also"></a>Vedere anche
--------

[Panoramica della Guida](help-overview.md)

[Panoramica sulla registrazione attività](../user-interface/task-recorder.md)

[Come creare una registrazione di attività da utilizzare per documentazione o formazione](../user-interface/task-recorder-training-docs.md)

[Creazione di nuove librerie di formazione per Dynamics 365 for Operations all'interno di Lifecycle Services mediante Registrazione attività (collegamento esterno)](https://docs.com/mufife/163372c6-f366-4c5a-94fa-93e2c25f878a/creating-new-training-libraries-for-dynamics-ax)


