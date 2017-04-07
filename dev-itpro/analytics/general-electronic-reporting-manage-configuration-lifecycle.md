---
title: Gestire il ciclo di vita delle configurazioni dei report elettronici
description: In questo argomento viene descritto come gestire il ciclo di vita delle configurazioni dichiarazioni elettroniche relative (ER) per Microsoft Dynamics 365 per la soluzione delle operazioni.
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ERDataModelDesigner, ERMappedFormatDesigner, ERModelMappingDesigner, ERModelMappingTable, ERSolutionImport, ERSolutionTable, ERVendorTable, ERWorkspace
audience: Application User, Developer, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 58801
ms.assetid: 35ad19ea-185d-4fce-b9cb-f94584b14f75
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: f4d8994f6548119789715a4879b6bc02d25598e9
ms.lasthandoff: 03/31/2017


---

# <a name="manage-the-electronic-reporting-configuration-lifecycle"></a>Gestire il ciclo di vita delle configurazioni dei report elettronici

In questo argomento viene descritto come gestire il ciclo di vita delle configurazioni dichiarazioni elettroniche relative (ER) per Microsoft Dynamics 365 per la soluzione delle operazioni.

<a name="overview"></a>Panoramica
--------

Creazione di report elettronici (ER, Electronic Reporting) è un motore che supporta i documenti elettronici specifici dei paesi e quelli richiesti dalla legge in Microsoft Dynamics 365 for Operations. In generale, ER presuppone la capacità di eseguire le seguenti attività per un singolo documento elettronico. Per ulteriori informazioni, vedere [] panoramica elettronica di report (general-electronic-reporting.md).

-   Progettare un modello per un documento elettronico:
    -   Identificare le origini dati necessarie che possono essere presentate nel documento:
        -   Dynamics sottostanti 365 per i dati di operazioni, ad esempio le tabelle dati, le entità di dati e le classi.
        -   proprietà specifiche seleziona, ad esempio la data di esecuzione e ora e fuso orario.
        -   Parametri di input utente, specificati dall'utilizzatore finale in fase di esecuzione.
    -   Definire gli elementi del documento necessari e relativa topologia per specificare un formato di documento finale.
    -   Configurare il flusso di dati desiderato dalle origini dati selezionate agli elementi del documento definiti (attraverso le associazioni delle origini dati ai componenti del formato documento) e specificare la logica di controllo del processo.
-   Rendere disponibile un modello in modo che possa essere utilizzato in altre istanze di Dynamics 365 for Operations:
    -   Trasformare un modello di documento creato in Dynamics 365 for Operations in una configurazione di ER ed esportare la configurazione dell'istanza corrente di Dynamics 365 for Operations come pacchetto XML che può essere archiviato in locale o in LCS.
    -   Trasformare una configurazione di ER in un modello di documento di Dynamics 365 for Operations.
    -   Importare un pacchetto XML archiviato in locale o in LCS nell'istanza corrente di Dynamics 365 for Operations.
-   Personalizzare il modello di un documento elettronico:
    -   Importare un modello da LCS nell'istanza corrente di Dynamics 365 for Operations come configurazione ER.
    -   Progettare una versione personalizzata di una configurazione ER e mantenere un riferimento alla versione di base.
-   Integrare un modello con un processo aziendale specifico, in modo che sia disponibile in Dynamics 365 for Operations:
    -   Configurare le impostazioni di Dynamics 365 for Operations in modo che inizi a utilizzare una configurazione di ER, facendo riferimento a quella configurazione in un parametro correlato al processo. Ad esempio, fare riferimento alla configurazione di ER in un metodo di pagamento specifico della contabilità fornitori per generare un messaggio di pagamento elettronico per l'elaborazione delle fatture.
-   Utilizzare un modello in un processo aziendale specifico:
    -   Eseguire una configurazione di ER in un processo aziendale specifico. Ad esempio, per generare un messaggio di pagamento elettronico per elaborare fattura quando un metodo di pagamento che fa riferimento alla configurazione di ER è selezionato.

## <a name="concepts"></a>Concetti
I ruoli seguenti e mansioni associate al ciclo di vita di configurazione di ER.

| Ruolo                                       | Attività                                                      | descrizione                                                                                                                                                                                                                  |
|--------------------------------------------|-----------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Consulente funzionale per la creazione di report elettronici | Creare e gestire i componenti di ER (modelli e formati).           | Un uomo d'affari che prevede i modelli dati specifici del dominio di ER, per i modelli necessari per i documenti elettronici e si associa di conseguenza.                                                                           |
| Sviluppatore per la creazione di report elettronici             | Creare e gestire i mapping del modello dati.                          | Dynamics 365 per lo specialista di operazioni che necessario selezionare Dynamics 365 per le origini dati delle operazioni e le associa ai modelli dati specifici del dominio di ER.                                                                 |
| Supervisore contabile                      | Configurare le impostazioni correlate ai processi che fa riferimento agli elementi ER. | Ad esempio, ** supervisore di contabilità ** un ruolo che consente alle impostazioni della configurazione di ER vengano utilizzate in particolare un metodo di pagamento della contabilità fornitori per generare un messaggio di pagamento elettronico per elaborare fattura. |
| Addetto pagamenti contabilità fornitori            | Utilizzare gli elementi ER in un processo aziendale specifico.                | Ad esempio, ** i pagamenti della contabilità fornitori clerk ** un ruolo che consente ai messaggi per pagamenti elettronici vengano generati per l'elaborazione delle fatture, in base al formato di ER configurato per un metodo di pagamento specifico.           |

## <a name="er-configuration-development-lifecycle"></a>Ciclo di vita di sviluppo della configurazione ER
Per i motivi correlati a ER seguenti, consigliamo di progettare le configurazioni ER nell'ambiente di sviluppo, come istanza separata di Dynamics 365 for Operations:

-   Gli utenti con il ruolo **Sviluppatore per la creazione di report elettronici** o **Consulente funzionale per la creazione di report elettronici** possono modificare le configurazioni ed eseguirle a scopo di test. Questo scenario può determinare chiamate a metodi di classi e tabelle che potrebbero essere potenzialmente pericolose per i dati aziendali e le prestazioni dell'istanza di Dynamics 365 for Operations.
-   Le chiamate a metodi di classi e tabelle come origini dati ER di configurazioni ER non sono limitate dai punti di ingresso di Dynamics 365 for Operations e dal contenuto della società registrata. Di conseguenza, gli utenti con il ruolo **Sviluppatore per la creazione di report elettronici** o **Consulente funzionale per la creazione di report elettronici** possono accedere a dati aziendali.

Le configurazioni di ER pianificate nell'ambiente di sviluppo possono essere caricate all'ambiente di test per la valutazione di configurazione (integrazione di lavorazione, di precisione dei risultati e le prestazioni) e il controllo della qualità, ad esempio la precisione noci diritti di accesso e dalla separazione dei compiti guidati da ruolo. Le funzionalità che consentono lo scambio di configurazione di ER è possibile utilizzare a tale scopo. Infine, le configurazioni tenta di ER possono essere un qualsiasi caricato a LC, in cui possono essere divise agli iscritti di assistenza, oppure all'ambiente di produzione per uso interno, come illustrato nella figura seguente. ![Ciclo di vita di configurazione di ER](./media/ger-configuration-lifecycle.png)

<a name="see-also"></a>Vedere anche
--------

[Panoramica sui report elettronici](general-electronic-reporting.md)


