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

In questo argomento vengono descritti i componenti della Guida di Microsoft Dynamics 365 per le operazioni. Consente di visualizzare una panoramica della procedura per connettere questi componenti e un riepilogo della creazione della Guida personalizzato. 

<a name="help-architecture"></a>Architettura della Guida
-----------------

Nell'illustrazione riportata delle parti di Dynamics 365 per il file della Guida delle operazioni. Nella Guida del prodotto recupera gli articoli da Dynamics 365 per il sito delle operazioni in https://docs.microsoft.com nonché l'attività manuale archiviato in Modellatore di processi aziendali nei servizi (LCS) del ciclo di vita. 
** Nota: ** Le funzionalità incluse nel diagramma con un asterisco (\*) pianificate, ma non sono ancora disponibili. [![Help architecture](./media/help-architecture.png)](./media/help-architecture.png)

## <a name="connecting-the-help-system"></a>Collegamento della Guida
Utilizzo ** parametri di sistema ** della pagina, gli amministratori di sistema alle parti della Guida relativa all'implementazione. [i parametri di sistema![il modulo con le impostazioni della Guida (]. /media/system-parameters_ops-1024x437.png)](. /media/system-parameters_ops.png) ** Parametri di sistema ** nella pagina, effettuare le seguenti operazioni:

1.  ** Importante: ** La prima volta che si accede ** Guida ** la scheda, è necessario connettersi ai servizi del ciclo di vita. Assicurarsi di fare clic sul collegamento tra al modulo, aspetti la connessione, chiudere la finestra di dialogo quindi fare clic su OK ** ** per ottenere ** parametri di sistema ** nella pagina. [! Collegamento a [] (LC. /media/connect-to-lcs-crop-1024x365.png "Accedono al" LC)](. /media/connect-to-lcs-crop.png)
2.  Selezionare il progetto Lifecycle Services a cui connettersi.
3.  Selezionare le librerie BPM (nel progetto selezionato) da cui recuperare le registrazioni attività.
4.  Impostare l'ordine di visualizzazione delle librerie BPM. Ciò determina l'ordine in cui le registrazioni attività delle librerie verranno visualizzate nel riquadro**Guida**.

Dopo il completamento di questi passaggi, è possibile aprire il riquadro **Guida** e fare clic sulla scheda **Guide attività**. Saranno ora visualizzate le guide attività applicabili alla pagina attualmente aperta in Dynamics 365 for Operations. Se non viene trovata alcuna guida attività, è possibile immettere le parole chiave per ridefinire la ricerca.

### <a name="showing-translated-task-guides"></a>Visualizzazione delle guide attività tradotte

Tramite tradotte di attività vengono innanzitutto state spedite nella raccolta unificata APQC del maggio 2016 e della raccolta iniziale. In Dynamics 365 for Operations, per visualizzare la guida attività localizzata, assicurarsi di essere connessi alla libreria di maggio. La lingua della Guida di attività viene visualizzata in è controllata per ciascun utente dalle impostazioni della lingua in ** opzioni ** &gt; ** delle preferenze **. **Nota:** anche se molte guide attività sono state tradotte, al momento il client Dynamics 365 for Operations non visualizza i nomi delle guide attività tradotte. Inoltre, solo per le aree di attività rilasciate nel febbraio 2016 sono disponibili nella traduzione in Raccolta di maggio. Si rilascerà una libreria aggiornata con traduzioni aggiuntive.

-   Se è stata tradotta una Guida attività, quando si apre la Guida attività tutto il testo apparirà nella lingua selezionata.
-   Se una Guida attività non è stata ancora tradotta, quando si apre solo parte del testo (quello dei controlli) apparirà nella lingua selezionata.

## <a name="creating-custom-help"></a>Creazione di una Guida personalizzata
È possibile creare la Guida personalizzata per l'implementazione di Dynamics 365 for Operations per creare registrazioni attività che riflettono l'implementazione e salvarle in una libreria di processi aziendali LCS. Per i partner, se si promuove una libreria a libreria aziendale e si include in una soluzione, sarà disponibile per i clienti. È inoltre possibile effettuare una copia della libreria globale unificata APQC e quindi aprire la copia, aprire le registrazioni attività dalla copia, modificarle e salvare le registrazioni con le modifiche. Per ulteriori informazioni, vedere [la creazione di un'attività registrata da utilizzare come documentazione o che si prepara (]. /user-interface/task-recorder.md).

<a name="see-also"></a>Vedere anche
--------

[Help overview](help-overview.md)

[Panoramica Registrazione attività. (]. /user-interface/task-recorder.md)

[Come creare una registrazione di attività da utilizzare per documentazione o formazione](../user-interface/task-recorder-training-docs.md)

[La creazione di nuove librerie di formazione per Dynamics 365 per le operazioni in servizi del ciclo di vita tramite Registrazione attività (collegamento esterno)](https://docs.com/mufife/163372c6-f366-4c5a-94fa-93e2c25f878a/creating-new-training-libraries-for-dynamics-ax)


