---
title: Componenti di Creazione di report elettronici
description: Questo argomento descrive i componenti di Creazione di report elettronici (ER).
author: nselin
ms.date: 09/28/2021
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 58941
ms.assetid: 5d51b6a6-ad12-4af9-a66d-a1eb820ae57f
ms.search.region: global
ms.topic: overview
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: aca1b9bbca490a8a9551ed97d6e100c9115a0d41
ms.sourcegitcommit: 753714ac0dabc4b7ce91509757cd19f7be4a4793
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/01/2022
ms.locfileid: "8367826"
---
# <a name="electronic-reporting-components"></a>Componenti di Creazione di report elettronici

[!include [banner](../includes/banner.md)]

Creazione di report elettronici (ER) supporta i seguenti tipi di componenti:

- Modello dati
- Mapping modello
- Formattazione
- Metadati

## <a name="data-model-component"></a>Componente modello dati

Il componente modello dati è una rappresentazione astratta di una struttura dati. Descrive un'area specifica del dominio aziendale con sufficienti dettagli per soddisfare le esigenze di reporting del dominio. Un componente modello dati è costituito dalle seguenti parti:

- **Modello di dati** - Un set di entità aziendali specifiche del dominio e una definizione con struttura gerarchica delle relazioni tra tali entità.
- **Mapping di modello** - Determinate origini dati dell'applicazione sono collegate a singoli elementi di un modello dati che specifica, al runtime, il flusso di dati e le regole per l'inserimento dei dati aziendali in un componente modello di dati.

L'entità aziendale di un modello di dati è rappresentata come contenitore o record. Le proprietà dell'entità aziendale sono rappresentate come elementi dati o campi. Ciascun elemento di dati dispone di un nome, un'etichetta, una descrizione e un valore univoci. Il valore di ogni elemento di dati può essere progettato in modo che venga riconosciuto come stringa, intero, reale, data, enumerazione o valore booleano. Inoltre, l'elemento di dati può essere un altro record o elenco di record.

Un singolo componente modello dati può contenere più gerarchie di entità aziendali specifiche del dominio. Può inoltre contenere i mapping di modello che supportano un flusso di dati specifico di un report al runtime. Le gerarchie vengono differenziate da un singolo record che è selezionato come radice del mapping di modello. Ad esempio, il modello dati dell'area del dominio pagamenti può supportare i mapping seguenti:


- Società \> Fornitore -\> Transazioni di pagamento del dominio Contabilità fornitori
- Cliente \> Società -\> Transazioni di pagamento del dominio Contabilità clienti

Le entità aziendali (ad esempio società e transazioni di pagamento) vengono progettate una sola volta. Mapping diversi possono riutilizzarle secondo necessità.

## <a name="model-mapping-component"></a>Componente di mapping del modello

Il mapping di modello collega determinate origini dati dell'applicazione a singoli elementi di un modello dati che specificano, al runtime, il flusso di dati e le regole per l'inserimento dei dati aziendali in un componente modello di dati.

Un mapping di modello che supporta documenti elettronici in uscita ha le seguenti funzionalità:

- È possibile utilizzare diversi tipi di dati come origini dati per un modello di dati. Questi tipi di dati includono tabelle, entità di dati, metodi ed enumerazioni.
- Supporta parametri di input dell'utente che possono essere definiti come origini dati del modello dati quando è necessario specificare alcuni dati al runtime.
- Supporta la trasformazione dei dati in gruppi richiesti. È inoltre possibile filtrare, ordinare e sommare i dati e aggiungere i campi calcolati logici progettati tramite formule simili alle formule di Microsoft Excel. Per ulteriori informazioni, vedere [Designer formula nella creazione di report elettronici (ER)](general-electronic-reporting-formula-designer.md).

Un mapping di modello che supporta documenti elettronici in entrata ha le seguenti funzionalità:

- Può includere elementi di dati aggiornabili diversi come obiettivi. Questi elementi dati includono tabelle, entità di dati e visualizzazioni. I dati possono essere aggiornati dai dati in entrata dei documenti elettronici. Diverse destinazioni possono essere utilizzate in un singolo mapping di modelli.
- Supporta parametri di input dell'utente che possono essere definiti come origini dati del modello dati quando è necessario specificare alcuni dati al runtime.

Un componente modello di dati è progettato per ogni dominio aziendale utilizzato come origine dati unificata per il reporting. L'origine dati unificata isola il reporting dall'implementazione fisica delle origini dati. Il componente rappresenta i concetti e le funzionalità aziendali specifici del dominio in una forma che rende più efficiente la progettazione iniziale dei formati di report e la successiva manutenzione.

## <a name="format-component"></a>Componente formato

### <a name="format-components-for-outgoing-electronic-documents"></a>Componenti di formato per i documenti elettronici in uscita

Un componente formato è lo schema dell'output della creazione di report che viene generato al runtime. Uno schema comprende i seguenti elementi:

- Un formato che definisce la struttura e il contenuto del documento elettronico in uscita generato al runtime.
- Origini dati come set di parametri di input dell'utente e un modello dati specifico del dominio che usa un mapping di modello selezionato
- Un mapping di formato come set di associazioni di origini dati di formato che hanno singoli elementi di un formato che specificano, al runtime, il flusso di dati e le regole per la generazione dell'output del formato.
- Una convalida del formato come set di regole configurabili che controllano la creazione di report al runtime, a seconda del contesto di esecuzione. Ad esempio, una regola che interrompe la generazione dell'output dei pagamenti di un fornitore e genera un'eccezione quando gli attributi specifici del fornitore selezionato sono mancanti, quali il numero di conto corrente bancario.

Un componente formato supporta le seguenti funzioni:

- Creazione di un output di report come singoli file in diversi formati, ad esempio testo, XML, documento di Microsoft Word o foglio di lavoro
- Creazione di più file separatamente e incapsulamento di tali file in file zip

Un componente formato consente di allegare file specifici che possono essere utilizzati nell'output di report:

- Cartekke di lavoro di Excel che contengono un foglio di lavoro utilizzabile come modello per output nel formato foglio di lavoro OPENXML.
- I file di Word che contengono un documento utilizzabile come modello per output nel formato documento di Microsoft Word.
- Altri file che è possibile incorporare nell'output del formato come file predefiniti.

Nella figura seguente viene illustrato il flusso dei dati per questi formati.

[![Flusso di dati per i componenti di formato in uscita](./media/ER-overview-02.png)](./media/ER-overview-02.png)

Per eseguire una singola configurazione di formato ER e generare un documento elettronico in uscita, è necessario identificare il mapping della configurazione di formato.

#### <a name="format-components-for-incoming-electronic-documents"></a>Componenti di formato per i documenti elettronici in entrata
Un componente di formato è lo schema del documento in entrata importato in fase di esecuzione. Uno schema comprende i seguenti elementi:

- Un formato che definisce la struttura e il contenuto del documento elettronico in entrata contenente i dati importati in fase di esecuzione. Un componente di formato viene utilizzato per analizzare un documento in entrata in vari formati, ad esempio testo e XML.
- Un mapping di formato che associa i singoli elementi di formato agli elementi di un modello dati specifico del dominio. In fase di esecuzione, gli elementi del modello dati specificano il flusso di dati e le regole per importare i dati da un documento in entrata e quindi archiviare i dati in un modello dati.
- Una convalida del formato come set di regole configurabili che controllano l'importazione dei dati in fase di esecuzione a seconda del contesto di esecuzione. Ad esempio, una regola che interrompe l'importazione dati di un rendiconto bancario con pagamenti di un fornitore e genera un'eccezione quando gli attributi di uno specifico fornitore sono mancanti, quali il codice di identificazione del fornitore.

Nella figura seguente viene illustrato il flusso dei dati per questi formati.

[![Flusso di dati per i componenti di formato in entrata](./media/ER-overview-03.png)](./media/ER-overview-03.png)

Per eseguire una singola configurazione di formato ER per importare i dati di un documento elettronico in entrata, è necessario identificare il mapping desiderato di una configurazione di formato e il punto di integrazione di un mapping di modello. È possibile utilizzare lo stesso mapping di modello e le destinazioni con i diversi formati per tipi diversi di documenti in entrata.


## <a name="component-versioning"></a>Controllo delle versioni del componente

Il controllo delle versioni è supportato per i componenti ER. Viene fornito il seguente flusso di lavoro per gestire le modifiche nei componenti ER:

1. La versione che viene creata in origine è contrassegnata come versione **Bozza**. Questa versione può essere modificata ed è disponibile per le esecuzioni dei test.
2. La versione **Bozza** può essere convertita in una versione **Completata**. Questa versione può essere utilizzata nei processi di creazione di report locali.
3. La versione **Completata** può essere convertita in una versione **Condivisa**. Questa versione viene pubblicata in Microsoft Dynamics Lifecycle Services (LCS) e può essere utilizzata nei processi globali di reporting.
4. La versione **Condivisa** può essere convertita in una versione **Interrotta**. Questa versione può essere eliminata.

Le versioni nello stato **Completata** o **Condivisa** sono disponibili per un altro interscambio di dati: Su un componente che dispone di questi stati è possibile eseguire queste azioni:

- Il componente può essere serializzato in formato XML ed esportato come file in formato XML.
- Il componente può essere nuovamente serializzato da un file XML e importato nell'applicazione come nuova versione di un componente di Creazione di report elettronici.

## <a name="component-date-effectivity"></a>Validità delle date dei componenti

Le versioni dei componenti ER dipendono dalle date. È possibile impostare la data di "Inizio validità" per un componente ER per specificare la data a partire dalla quale il componente diventa valido per i processi di creazione di report. La data della sessione dell'applicazione viene utilizzata per definire se un componente è valido per l'esecuzione. Se più di una versione è valida per una data specifica, la versione più recente viene utilizzata per i processi di creazione di report.

## <a name="component-access"></a>Accesso ai componenti

L'accesso ai componenti di formato ER dipende dall'impostazione del codice del paese/area geografica dell'organizzazione internazionale per la standardizzazione (ISO, International Organization for Standardization). Se questa impostazione è vuota per la versione selezionata di una configurazione di formato, un componente formato è accessibile da qualsiasi società al runtime. Se l'impostazione contiene codici di paese/area geografica ISO, il componente formato è disponibile solo dalle società che hanno un indirizzo principale definito per uno dei codici di paese/area geografica ISO del componente formato.

Versioni differenti di un componente formato dati possono avere impostazioni differenti per i codici di paese ISO.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

