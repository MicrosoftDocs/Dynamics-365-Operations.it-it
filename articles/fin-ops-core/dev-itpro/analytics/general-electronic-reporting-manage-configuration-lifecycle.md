---
title: Gestire il ciclo di vita della configurazione per la creazione di report elettronici
description: In questo articolo viene descritto come gestire il ciclo di vita delle configurazioni ER per Dynamics 365 Finance.
author: kfend
ms.date: 07/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58801
ms.assetid: 35ad19ea-185d-4fce-b9cb-f94584b14f75
ms.search.form: ERDataModelDesigner, ERMappedFormatDesigner, ERModelMappingDesigner, ERModelMappingTable, ERSolutionImport, ERSolutionTable, ERVendorTable, ERWorkspace
ms.openlocfilehash: 0209679c9882d87edab68d043fba9e7b3400a2a2
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2022
ms.locfileid: "9337195"
---
# <a name="manage-the-electronic-reporting-er-configuration-lifecycle"></a>Gestire il ciclo di vita della configurazione per la creazione di report elettronici

[!include [banner](../includes/banner.md)]

In questo articolo viene descritto come gestire il ciclo di vita delle [configurazioni](general-electronic-reporting.md#Configuration) per la [creazione di report elettronici](general-electronic-reporting.md) (ER) per Dynamics 365 Finance.

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

    - Trasformare un modello di documento creato in una configurazione di ER ed esportare la configurazione dell'istanza corrente dell'applicazione come pacchetto XML che può essere archiviato in locale o in Lifecycle Services (LCS).
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
Per i motivi correlati a ER seguenti, consigliamo di progettare le configurazioni ER nell'ambiente di sviluppo, come istanza separata di finanza e operazioni:

- Gli utenti con il ruolo **Sviluppatore per la creazione di report elettronici** o **Consulente funzionale per la creazione di report elettronici** possono modificare le configurazioni ed eseguirle a scopo di test. Questo scenario può determinare chiamate a metodi di classi e tabelle che potrebbero essere potenzialmente pericolose per i dati aziendali e le prestazioni dell'istanza.
- Le chiamate a metodi di classi e tabelle come origini dati ER di configurazioni ER non sono limitate dai punti di ingresso e dal contenuto aziendale registrato. Di conseguenza, gli utenti con il ruolo **Sviluppatore per la creazione di report elettronici** o **Consulente funzionale per la creazione di report elettronici** possono accedere a dati aziendali.

Le configurazioni ER progettate nell'ambiente di sviluppo possono essere [caricate](#data-persistence-consideration) nell'ambiente di test per la valutazione della configurazione (integrazione del processo appropriata, correttezza dei risultati, prestazioni) e il controllo della qualità (correttezza dei diritti di accesso basati sui ruoli, separazione dei compiti). Le funzionalità che consentono lo scambio di configurazioni ER possono essere utilizzate a tale scopo. Le configurazioni ER testate possono essere caricate in LCS per essere condivise con gli abbonati al servizio oppure possono essere [importate](#data-persistence-consideration) nell'ambiente di produzione per uso interno.

![Ciclo di vita della configurazione ER.](./media/ger-configuration-lifecycle.png)

## <a name="data-persistence-consideration"></a>Considerazione sulla persistenza dei dati

Puoi [importare](tasks/er-import-configuration-lifecycle-services.md) individualmente differenti versioni di una [configurazione](general-electronic-reporting.md#Configuration) ER nell'istanza di Finance. Quando viene importata una nuova versione di una configurazione ER, il sistema controlla il contenuto della versione bozza di questa configurazione:

- Quando la versione importata è inferiore alla versione più alta di questa configurazione nell'istanza corrente di Finance, il contenuto della versione bozza di questa configurazione rimane invariato.
- Quando la versione importata è superiore a qualsiasi altra versione di questa configurazione nell'istanza corrente di Finance, il contenuto della versione importata viene copiato nella versione bozza di questa configurazione per continuare a modificare l'ultima versione completata.

Se questa configurazione è di proprietà del [provider](general-electronic-reporting.md#Provider) di configurazioni attualmente attivato, la versione bozza di questa configurazione è visibile nella Scheda dettaglio **Versioni** della pagina **Configurazioni** (**Amministrazione organizzazione** > **Creazione di report elettronici** > **Configurazioni**). È possibile selezionare la versione bozza della configurazione e [modificarne](er-quick-start2-customize-report.md#ConfigureDerivedFormat) il contenuto utilizzando il designer ER pertinente. Dopo la modifica della versione bozza di una configurazione ER, il relativo contenuto non corrisponde più al contenuto della versione più alta di questa configurazione nell'istanza corrente di Finance. Per evitare la perdita delle modifiche, il sistema visualizza un errore indicante che l'importazione non è in grado di continuare poiché la versione di questa configurazione è superiore alla versione più alta di questa configurazione nell'istanza corrente di Finance. Quando ciò accade, ad esempio con la configurazione del formato **X**, viene visualizzato l'errore **Versione del formato "X" non completata**.

Per annullare le modifiche introdotte nella versione bozza, selezionare la versione completata o condivisa più alta della configurazione ER in Finance nella Scheda dettaglio **Versioni**, quindi selezionare l'opzione **Ottieni questa versione**. Il contenuto della versione selezionata viene copiato nella versione bozza.

## <a name="applicability-consideration"></a>Considerazione sull'applicabilità

Quando si progetta una nuova versione di una configurazione ER, puoi definirne la [dipendenza](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md) da altri componenti software. Questo passaggio è considerato un prerequisito per il controllo del download di questa versione della configurazione da un repository ER o un file XML esterno e per qualsiasi altro utilizzo della versione. Quando tenti di importare una nuova versione di una configurazione ER, il sistema utilizza i prerequisiti configurati per controllare se la versione può essere importata.

In alcuni casi, potrebbe essere necessario che il sistema ignori i prerequisiti configurati quando si importano nuove versioni delle configurazioni ER. Per fare in modo che il sistema ignori i prerequisiti durante l'importazione, segui questi passaggi.

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nel Riquadro azioni, nella scheda **Configurazioni**, nel gruppo **Impostazioni avanzate**, selezionare **Parametri utente**.
3. Imposta l'opzione **Ignora gli aggiornamenti del prodotto e il controllo dei prerequisiti della versione durante l'importazione** su **Sì**.

    > [!NOTE]
    > Questo parametro è specifico dell'utente e dell'azienda.

## <a name="dependencies-on-other-components"></a>Dipendenze da altri componenti

Le configurazioni ER possono essere configurate come [dipendenti](er-download-configurations-global-repo.md#import-filtered-configurations) da altre configurazioni. Ad esempio, puoi [importare](er-download-configurations-global-repo.md) una configurazione del [modello di dati](er-overview-components.md#data-model-component) ER dal repository globale nell'istanza [Microsoft Regulatory Configuration Services (RCS)](../../../finance/localizations/rcs-overview.md) o Dynamics 365 Finance, quindi creare una nuova configurazione di [formato](er-overview-components.md#format-component) ER [derivata](er-quick-start2-customize-report.md#DeriveProvidedFormat) dalla configurazione del modello di dati ER importata. La configurazione di formato ER derivata dipenderà dalla configurazione del modello di dati ER di base.

![Configurazione di formato ER derivata nella pagina Configurazioni.](./media/ger-configuration-lifecycle-img1.png)

Al termine della progettazione del formato, puoi cambiare lo stato della versione iniziale della configurazione di formato ER da **Bozza** a **Completata**. Puoi quindi condividere la versione completata della configurazione di formato ER [pubblicandola](../../../finance/localizations/rcs-global-repo-upload.md) nel repository globale. Successivamente, puoi accedere al repository globale da qualsiasi istanza cloud RCS o Finance. Puoi quindi importare qualsiasi versione della configurazione ER applicabile all'applicazione dal repository globale in tale applicazione.

![Configurazione di formato ER pubblicata nella pagina Archivio di configurazioni.](./media/ger-configuration-lifecycle-img2.png)

In base alla dipendenza dalla configurazione, quando selezioni la configurazione di formato ER nel repository globale per importarla in un'istanza RCS o Finance appena distribuita, la configurazione del modello di dati ER di base viene trovata automaticamente nel repository globale e importata insieme alla configurazione di formato ER selezionata come configurazione di base.

Puoi anche esportare la versione della configurazione di formato ER dall'istanza RCS o Finance corrente e archiviarla localmente come file XML.

![Esportazione della versione di una configurazione di formato ER come file XML nella pagina Configurazioni.](./media/ger-configuration-lifecycle-img3.png)

Nelle versioni di Finance **antecedenti alla versione 10.0.29**, quando tenti di importare la versione della configurazione di formato ER da quel file XML o da qualsiasi repository che non sia il repository globale in un'istanza RCS o Finance appena distribuita che non contiene ancora alcuna configurazione ER, verrà generata la seguente eccezione per informarti dell'impossibilità di ottenere una configurazione di base:

> Riferimenti non risolti rimanenti<br>
Impossibile stabilire il riferimento dell'oggetto '\<imported configuration name\>' all'oggetto "Base" (\<globally unique identifier of the missed base configuration\>,\<version of the missed base configuration\>)

![Importazione della versione della configurazione di formato ER nella pagina Archivio di configurazioni.](./media/ger-configuration-lifecycle-img4.gif)

Nella versione **10.0.29 e successive**, quando tenti di eseguire la stessa importazione della configurazione, se non è possibile trovare una configurazione di base nell'istanza dell'applicazione corrente o nel repository di origine attualmente in uso (se applicabile), il framework ER proverà automaticamente a trovare il nome della configurazione di base mancante nella cache del repository globale. Presenterà quindi il nome e l'identificatore univoco globale (GUID) della configurazione di base mancante nel testo dell'eccezione generata.

> Riferimenti non risolti rimanenti<br>
Impossibile stabilire il riferimento dell'oggetto '\<imported configuration name\>' all'oggetto 'Base' (\<name of the missed base configuration\> \<globally unique identifier of the missed base configuration\>,\<version of the missed base configuration\>)

![Eccezione nella pagina Archivio di configurazioni quando non è possibile trovare la configurazione di base.](./media/ger-configuration-lifecycle-img5.png)

Puoi utilizzare il nome fornito per trovare la configurazione di base e quindi importarla manualmente.

> [!NOTE]
> Questa nuova opzione funziona solo quando almeno un utente ha già effettuato l'accesso al repository globale usando la pagina [Archivi di configurazioni](er-download-configurations-global-repo.md#open-configurations-repository) o uno dei campi di [ricerca](er-extended-format-lookup.md) del repository globale nell'istanza Finance corrente e quando il contenuto del repository globale è stato memorizzato nella cache.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della creazione di report elettronici](general-electronic-reporting.md)

[Definire la dipendenza delle configurazioni ER in altri componenti](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

