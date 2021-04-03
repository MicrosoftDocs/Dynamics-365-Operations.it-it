---
title: Gestire il ciclo di vita della configurazione per la creazione di report elettronici (ER)
description: In questo argomento viene descritto come gestire il ciclo di vita delle configurazioni ER per la soluzione Microsoft Dynamics 365 Finance.
author: NickSelin
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERMappedFormatDesigner, ERModelMappingDesigner, ERModelMappingTable, ERSolutionImport, ERSolutionTable, ERVendorTable, ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 58801
ms.assetid: 35ad19ea-185d-4fce-b9cb-f94584b14f75
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3b1b5ac8e256835332a4c53ed2872ee609253ad9
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5568727"
---
# <a name="manage-the-electronic-reporting-er-configuration-lifecycle"></a>Gestire il ciclo di vita della configurazione per la creazione di report elettronici (ER)

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come gestire il ciclo di vita delle configurazioni ER per Microsoft Dynamics 365 Finance.

## <a name="overview"></a>Panoramica

Creazione di report elettronici (ER, Electronic Reporting) è un motore che supporta i documenti elettronici specifici dei paesi e quelli richiesti dalla legge. In generale, ER presuppone la capacità di eseguire le seguenti attività per un singolo documento elettronico. Per ulteriori informazioni, vedere [Panoramica dello strumento di creazione di report elettronici](general-electronic-reporting.md).

- Progettare un modello per un documento elettronico:

    - Identificare le origini dati necessarie che possono essere presentate nel documento:

        - Dati sottostanti, come tabelle dati, entità di dati e classi.
        - Proprietà specifiche del processo, come data e ora di esecuzione e fuso orario.
        - Parametri di input utente, specificati dall'utente finale in fase di esecuzione.

    - Definire gli elementi del documento necessari e relativa topologia per specificare un formato di documento finale.
    - Configurare il flusso di dati desiderato dalle origini dati selezionate agli elementi del documento definiti (attraverso le associazioni delle origini dati ai componenti del formato documento) e specificare la logica di controllo del processo.

- Rendere disponibile un modello in modo che possa essere utilizzato in altre istanze:

    - Trasformare un modello di documento creato in una configurazione di ER ed esportare la configurazione dell'istanza corrente dell'applicazione come pacchetto XML che può essere archiviato in locale o in LCS.
    - Trasformare una configurazione di ER in un modello di documento dell'applicazione.
    - Importare un pacchetto XML archiviato in locale o in LCS dell'istanza corrente.

- Personalizzare il modello di un documento elettronico:

    - Importare un modello da LCS nell'istanza corrente come configurazione ER.
    - Progettare una versione personalizzata di una configurazione ER e mantenere un riferimento alla versione di base.

- Integrare un modello con un processo aziendale specifico, in modo che sia disponibile nell'applicazione:

    - Configurare le impostazioni dell'applicazione in modo che inizi a utilizzare una configurazione di ER, facendo riferimento a quella configurazione in un parametro correlato al processo. Ad esempio, fare riferimento alla configurazione ER in un metodo di pagamento contabilità fornitori specifico per generare un messaggio di pagamento elettronico per l'elaborazione delle fatture.

- Utilizzare un modello in un processo aziendale specifico:

    - Eseguire una configurazione di ER in un processo aziendale specifico. Ad esempio, per generare un messaggio di pagamento elettronico per l'elaborazione delle fatture quando è selezionato un metodo di pagamento che fa riferimento alla configurazione ER.

## <a name="concepts"></a>Concetti
I seguenti ruoli e attività correlate sono associati al ciclo di vita di una configurazione ER:

| Ruolo                                       | Attività                                                      | Descrizione |
|--------------------------------------------|-----------------------------------------------------------------|-------------|
| Consulente funzionale per la creazione di report elettronici | Creare e gestire i componenti di ER (modelli e formati).           | Una persona che progetta i modelli di dati specifici del dominio di ER, progetta i modelli necessari per i documenti elettronici e li associa di conseguenza. |
| Sviluppatore per la creazione di report elettronici             | Creare e gestire i mapping del modello dati.                          | Uno specialista che seleziona le origini dati di Finance necessarie e le associa ai modelli di dati specifici del dominio ER |
| Supervisore contabile                      | Configurare le impostazioni correlate ai processi che fa riferimento agli elementi ER. | Ad esempio, il ruolo **Supervisore di contabilità** che consente di utilizzare le impostazioni di una configurazione di ER da utilizzare in un metodo di pagamento contabilità fornitori per generare un messaggio di pagamento elettronico per l'elaborazione delle fatture |
| Addetto pagamenti contabilità fornitori            | Utilizzare gli elementi ER in un processo aziendale specifico.                | Ad esempio, il ruolo **Addetto pagamenti contabilità fornitori** che consente di generare messaggi di pagamento elettronico per l'elaborazione delle fatture, in base al formato ER configurato per un metodo di pagamento specifico. |

## <a name="er-configuration-development-lifecycle"></a>Ciclo di vita di sviluppo della configurazione ER
Per i motivi ER seguenti, consigliamo di progettare le configurazioni ER nell'ambiente di sviluppo, come istanza separata di Finance and Operations:

- Gli utenti con il ruolo **Sviluppatore per la creazione di report elettronici** o **Consulente funzionale per la creazione di report elettronici** possono modificare le configurazioni ed eseguirle a scopo di test. Questo scenario può determinare chiamate a metodi di classi e tabelle che potrebbero essere potenzialmente pericolose per i dati aziendali e le prestazioni dell'istanza.
- Le chiamate a metodi di classi e tabelle come origini dati ER di configurazioni ER non sono limitate dai punti di ingresso e dal contenuto aziendale registrato. Di conseguenza, gli utenti con il ruolo **Sviluppatore per la creazione di report elettronici** o **Consulente funzionale per la creazione di report elettronici** possono accedere a dati aziendali.

Le configurazioni ER progettate nell'ambiente di sviluppo possono essere caricate nell'ambiente di test per la valutazione della configurazione (integrazione del processo appropriata, correttezza dei risultati, prestazioni) e il controllo della qualità (correttezza dei diritti di accesso basati sui ruoli, separazione dei compiti). Le funzionalità che consentono lo scambio di configurazioni ER possono essere utilizzate a tale scopo. Infine, le configurazioni ER testate possono essere caricate in LCS, dove possono essere condivise con i sottoscrittori al servizio o nell'ambiente di produzione per uso interno, come illustrato nella seguente figura.

![Ciclo di vita della configurazione ER](./media/ger-configuration-lifecycle.png)

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica dello strumento di creazione di report elettronici](general-electronic-reporting.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]