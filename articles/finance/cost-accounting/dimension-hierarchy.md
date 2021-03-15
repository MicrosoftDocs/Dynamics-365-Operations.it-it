---
title: Gerarchia dimensioni
description: In questo argomento vengono fornite informazioni sulle gerarchie di dimensioni. È possibile utilizzare una gerarchia di dimensioni per definire la struttura di report, i criteri di costo e l'impostazione di sicurezza nella contabilità industriale.
author: AndersGirke
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimensionHierarchy,
audience: Application User
ms.reviewer: roschlom
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 7fde19ad1a58616672de72fb5e5cbeea39138b46
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4995192"
---
# <a name="dimension-hierarchy"></a>Gerarchia dimensioni

[!include [banner](../includes/banner.md)]

In questo argomento vengono fornite informazioni sulle gerarchie di dimensioni. È possibile utilizzare una gerarchia di dimensioni per definire la struttura di report, i criteri di costo e l'impostazione di sicurezza nella contabilità industriale.  

## <a name="overview"></a>Panoramica

Le gerarchie di dimensioni vengono utilizzate in varie posizioni nella contabilità industriale. Una gerarchia di dimensioni consente di definire le seguenti informazioni:

-  La struttura di report che soddisfa i requisiti dell'organizzazione
-  Criteri di costo
-  Impostazione di sicurezza

Di seguito è riportato un esempio di gerarchia di dimensioni.

![Esempio di gerarchia di dimensioni](./media/dimension-hierarchy.png)

Una gerarchia di dimensioni può essere creata per i seguenti tipi di dimensioni:

-  Dimensioni elemento di costo
-  Dimensioni oggetto di costo
-  Dimensioni statistiche

> [!NOTE]
> - È possibile creare più gerarchie di dimensioni per la stessa dimensione se diverse prospettive sono richieste.
> - Una gerarchia di dimensioni può essere associata a una sola dimensione.
> - Una gerarchia di dimensioni può avere illimitati livelli nella struttura. Tutti i livelli saranno disponibili nell'area di lavoro **Controllo costi**. Quando si utilizza Microsoft Excel o Microsoft Power BI per la creazione di report, solo i primi 15 livelli della gerarchia di dimensioni vengono esportati. Questa limitazione esiste perché sia Excel sia Power BI richiedono uno schema fisso.
> - Una gerarchia di dimensioni non ha date di validità. Pertanto, qualsiasi modifica a una gerarchia di dimensioni viene immediatamente salvata nel record e non è possibile effettuare il confronto prima della data e dopo la data.

## <a name="dimension-hierarchy-type"></a>Tipo di gerarchie di dimensioni

Quando si crea una nuova gerarchia di dimensioni, è necessario selezionare un tipo di gerarchia. Passare a **Contabilità industriale** > **Dimensioni** > **Gerarchie di dimensioni**. Fare clic **Nuovo** e selezionare un tipo di gerarchia di dimensioni. È possibile selezionare **Gerarchia di categorie di dimensioni** o **Gerarchia classificazioni dimensione**.

### <a name="dimension-categorization-hierarchy"></a>Gerarchia di categorie di dimensioni

Il tipo **Gerarchia di categorie di dimensioni** viene utilizzato per il reporting. Supporta solo le dimensioni elemento di costo. Quando si seleziona questo tipo, si applicano le regole seguenti:

-  Un membro di dimensione può essere associato più volte nella struttura gerarchica.
-  È possibile inserire un membro di dimensione elemento di costo in nodi diversi assegnando un comportamento di costo al nodo foglia.

### <a name="dimension-classification-hierarchy"></a>Gerarchia classificazioni dimensione

Il tipo **Gerarchia classificazioni dimensione** viene utilizzato per definire regole e per il reporting. Supporta tutte le dimensioni, quali gli oggetti di costo, gli elementi di costo e le dimensioni statistiche. Quando si seleziona questo tipo, un membro di dimensione può essere associato solo una volta nella struttura gerarchica.

## <a name="create-and-maintain-a-dimension-hierarchy"></a>Creare e gestire una gerarchia di dimensioni

Una gerarchia di dimensioni viene creata come struttura ad albero con le relazioni tra nodo e nodi foglia.

-  Un nodo può avere 1:_n_ sottonodi.
-  Un nodo non può avere sottonodi e nodi foglia assegnati.
-  Un nodo foglia può essere assegnato solo al livello più basso nella gerarchia.

### <a name="example"></a>Esempio

Una società di piccole dimensioni ha la seguente struttura organizzativa, in cui Finanza e Risorse umane sono reparti in Amministrazione e Assemblaggio e Imballaggio sono i reparti in Produzione.

![Esempio di struttura di un'organizzazione](./media/dimension-hierarchy-org.png)

Una dimensione oggetto di costo rappresenta tutti i centri di costo dell'organizzazione.

- Dimensione oggetto di costo
    - Centri di costo

La dimensione oggetto di costi che rappresenta tutti i centri di costo può essere impostata come indicato di seguito.

| Centri di costo | descrizione |
|--------------|-------------|
| CC001        | Risorse umane          |
| CC002        | Dati finanziari     |
| CC003        | Imposta sul reddito         |
| CC007        | AR/AP       |
| CC005        | Assemblaggio    |
| CC006        | Imballaggio   |

Una dimensione elemento di costo rappresenta tutti gli elementi di costo dell'organizzazione.

- Dimensione elemento di costo
    - Elementi di costo

La dimensione elemento di costi che rappresenta tutti gli elementi di costo può essere impostata come indicato di seguito.

| Elementi di costo | descrizione |
|---------------|-------------|
| 10001         | Elettricità |
| 10010         | Pulizia    |
| 10011         | Riscaldamento     |
| 40001         | COGS        |

Una gerarchia di dimensioni che soddisfa i requisiti di reporting dell'organizzazione può essere impostata come indicato di seguito.

**Dettagli gerarchia dimensioni**

| Nome gerarchia dimensioni | Dimensione    | Nome tipo di gerarchia dimensioni      | Gerarchia elenco accessi |
|--------------------------|--------------|------------------------------------|-----------------------|
| Organizzazione             | Centri di costo | Gerarchia classificazioni dimensione | No                    |

La gerarchia di dimensioni per il reporting può essere impostata come indicato di seguito.

|                   | Intervalli membro di dimensione   |                         |
|-------------------|---------------------------|-------------------------|
| **Nodi**         | **Membro di dimensione di inizio** | **Membro di dimensione di fine** |
| Organizzazione      |                           |                         |
| &nbsp;&nbsp;Amministratore         |                           |                         |
|&nbsp;&nbsp;&nbsp;&nbsp;Dati finanziari   | CC002                     | CC003                   |
|                   | CC007                     | CC007                   |
| &nbsp;&nbsp;&nbsp;&nbsp;Risorse umane        | CC001                     | CC001                   |
| &nbsp;&nbsp;Produzione    |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Imballaggio | CC005                     | CC005                   |
| &nbsp;&nbsp;&nbsp;&nbsp;Assemblaggio  | CC006                     | CC006                   |

Una gerarchia di dimensioni che soddisfa i requisiti di criteri può essere impostata come indicato di seguito.

**Dettagli gerarchia dimensioni**

| Nome gerarchia dimensioni | Dimensione     | Nome tipo di gerarchia dimensioni      |
|--------------------------|---------------|------------------------------------|
| Comportamento costo            | Elementi di costo | Gerarchia classificazioni dimensione |

La gerarchia di dimensioni per i criteri può essere impostata come indicato di seguito.

|                   | Intervalli membro di dimensione   |                         |
|-------------------|---------------------------|-------------------------|
| **Nodi**         | **Membro di dimensione di inizio** | **Membro di dimensione di fine** |
| Comportamento costo     |                           |                         |
| &nbsp;&nbsp;Costo fisso    | 10001                     | 10011                   |
|&nbsp;&nbsp;Costo variabile | 40001                     | 40010                   |

> [!NOTE]
> Sotto **Intervalli membro di dimensione**, un nodo può contenere 1:_n_ intervalli membro di dimensione. È possibile inserire ID membro di dimensione non ancora esistenti come membri di dimensione. Questo comportamento rende la gerarchia resiliente per il futuro.  

### <a name="copy-a-hierarchy"></a>Copiare una gerarchia

È possibile copiare una gerarchia di dimensioni corrente come punto di partenza per una nuova gerarchia di dimensioni. Questo comportamento può risultare utile se si desidera confrontare la gerarchia di dimensioni precedente con la nuova gerarchia di dimensioni.

### <a name="rearrange-nodes-in-a-hierarchy"></a>Ridisporre i nodi in una gerarchia

È possibile spostare un nodo verso l'alto e verso il basso all'interno del livello corrente della struttura. In questo modo, è possibile ridisporre i nodi per la dichiarazione nell'area di lavoro **Controllo costi**.

Spostare un nodo in una nuova posizione nella gerarchia selezionando il nodo di destinazione. Per spostare un nodo sono disponibili i due seguenti metodi:

- **Sposta sotto** - Spostare il nodo selezionato dalla posizione corrente nella gerarchia e inserirlo **sotto** il nodo di destinazione selezionato.
- **Sposta dopo** - Spostare il nodo selezionato dalla posizione corrente nella gerarchia e inserirlo **dopo** il nodo di destinazione selezionato al livello della gerarchia.

> [!NOTE] 
> L'ordine dei nodi non viene mantenuto quando si esportano i dati in Excel o Power BI perché gli strumenti utilizzano un criterio di ordinamento alfanumerico per impostazione predefinita. È necessario modificare manualmente l'ordine.

## <a name="define-dimension-hierarchies-for-reporting"></a>Definire le gerarchie di dimensioni per il reporting

Le gerarchie di dimensioni sono importanti per il reporting. Consentono di definire la struttura specifica adatta alla singola organizzazione. Le aggregazioni apportate a livello di nodo della gerarchia di dimensioni consentono alle parti interessate a qualsiasi livello dell'organizzazione di vedere i dati a qualsiasi livello.

Le gerarchie di dimensioni sono disponibili nei seguenti strumenti di report. Questo comportamento contribuisce a garantire la coerenza nella struttura di reporting.

- Area di lavoro **Controllo costi** (client):

    - Controllata dalla configurazione.

- Area di lavoro **Controllo costi** (applicazione mobile):

    - Controllata dalla configurazione.

- Excel

    - Consente di selezionare le gerarchie di dimensioni specifiche per la definizione dell'esportazione:

        - Una gerarchia dimensioni di elemento di costo (obbligatoria)
        - Una gerarchia dimensioni di oggetto di costo (facoltativa)
        - Una gerarchia dimensioni statistiche (facoltativa)

- Power BI:

    - Tutte le gerarchie di dimensioni sono disponibili.
    
Se si creano report utilizzando Excel o Power BI, solo i primi 15 livelli di gerarchie di dimensioni vengono esportati. Questa limitazione esiste perché Excel e Power BI richiedono uno schema fisso. Se una gerarchia ha più di 15 livelli, i livelli aggiuntivi non verranno esportati. La tabella normalizzata contiene un record per ogni membro di dimensione della gerarchia. Di conseguenza, viene eseguita l'aggregazione automatica. Questo comportamento assicura che i saldi di uno qualsiasi dei 15 livelli disponibili nella gerarchia sono corretti.

Nell'esempio seguente viene illustrata una gerarchia di dimensioni nella struttura di reporting.

| Gerarchia dimensioni di oggetto di costo - Livello 1 | Gerarchia dimensioni di oggetto di costo - Livello 2 | Gerarchia dimensioni di oggetto di costo - Livello 3 | Gerarchia dimensioni di oggetto di costo - Livello 4 | Gerarchia dimensioni di oggetto di costo - Livello 15 |
|-------------------------------------------|-------------------------------------------|-------------------------------------------|-------------------------------------------|--------------------------------------------|
| Organizzazione                              | Amministratore                                     | Dati finanziari                                   | CC002                                     |                                            |
| Organizzazione                              | Amministratore                                     | Dati finanziari                                   | CC003                                     |                                            |
| Organizzazione                              | Amministratore                                     | Dati finanziari                                   | CC007                                     |                                            |
| Organizzazione                              | Amministratore                                     | Risorse umane                                        | CC001                                     |                                            |
| Organizzazione                              | Produzione                                | Imballaggio                                 | CC005                                     |                                            |
| Organizzazione                              | Produzione                                | Assemblaggio                                  | CC006                                     |                                            |

### <a name="update-the-dimension-hierarchies-that-are-used-for-reporting"></a>Aggiornare gerarchie di dimensioni utilizzate per il reporting 

Nel tempo, le gerarchie di dimensioni utilizzate in precedenza per gli strumenti di report indicati dovranno essere aggiornate. È possibile aggiornare le gerarchie di dimensioni aggiornando il client.

- Area di lavoro **Controllo costi** (client)
- Area di lavoro **Controllo costi** (applicazione mobile)

Gli aggiornamenti alle gerarchie di dimensioni vengono selezionati ogni 24 ore da un processo precedente alla memorizzazione nella cache. Dopo che i dati esportati vengono aggiornati, le gerarchie di dimensioni aggiornate sono disponibili nei seguenti strumenti:

- Excel
- Power BI

> [!NOTE] 
> Per attivare manualmente un aggiornamento della cache della gerarchia di dimensioni, è possibile creare una nuova esportazione in Excel per la gerarchia di dimensioni o le gerarchie che devono essere aggiornate.

## <a name="define-dimension-hierarchies-for-cost-policies"></a>Definire le gerarchie di dimensioni per i criteri di costo

La contabilità industriale è costituita da più criteri in cui vengono definite le regole dettagliate. È necessario definire una o più gerarchie di dimensioni per i seguenti criteri:

- Comportamento costo
- Distribuzione costi
- Allocazione costi
- Rollup costi

Le gerarchie di dimensioni rendono più semplice la creazione delle regole. Per evitare di creare regole per ogni membro di dimensione è possibile utilizzare le aggregazioni dei membri di dimensione fornite dai livelli della gerarchia di dimensioni. Se si dispone di regole di sovrapposizione, è necessario definire le regole specifiche utilizzate dal sistema per il calcolo dei costi generali.

### <a name="example-define-a-cost-behavior-policy"></a>Esempio: Definire i criteri di comportamento costo

I nuovi criteri di comportamento costo vengono creati e le gerarchie di dimensioni appropriate vengono assegnate ai criteri, come illustrato di seguito.

**Criteri di comportamento costo**

| Nome criteri   | Gerarchia dimensioni di elemento di costo | Gerarchia dimensioni di oggetto di costo | Valuta di contabilizzazione |
|---------------|----------------------------------|---------------------------------|---------------------|
| Comportamento costo | Comportamento costo                    | Organizzazione                    | GBP                 |

**Regole**

| Nodo gerarchia dimensioni di elemento di costo | Nodo gerarchia dimensioni di oggetto di costo | Percentuale fissa | Importo fisso | Data di inizio validità | Data di fine validità |
|---------------------------------------|--------------------------------------|------------------|--------------|------------|----------|
| Costo fisso                            | Organizzazione                         | 100,00           | 0,00         | 1/1/2017   | Mai    |
| 10001                                 | Organizzazione                         | 0,00             | 150,00       | 1/1/2017   | Mai    |
| 10001 (\*)                             | Dati finanziari                              |                  | 50,00        | 1/1/2017   | Mai    |
| Comportamento costo o Costo variabile (\*\*)   | Organizzazione                         | 0,00             | 0,00         | 1/1/2017   | Mai    |

\* Il nodo del costo variabile non è obbligatorio. Se il costo non viene classificato come costo fisso, deve essere un costo variabile.

\*\* Una regola dettagliata verrà creata per la combinazione del membro di elemento di costo 10001 e tutti i membri oggetti di costo aggregati nel livello di gerarchia Dati finanziari (CC002, CC003, CC007).

Le regole precedenti indicano la flessibilità fornita dalle gerarchie di dimensioni. Definendo regole di alto livello è possibile ridurre la manutenzione. È possibile definire le regole dettagliate per soddisfare un obiettivo aziendale specifico.

Se le gerarchie di dimensioni utilizzate nelle regole vengono aggiornate, il sistema porta automaticamente gli aggiornamenti in avanti.

Se un livello di granularità delle regole non è più richiesto, è possibile far scadere la regola.

Ad esempio, una regola di comportamento costo specifica per il nodo di gerarchia di dimensioni oggetto di costo Dati finanziari non è più richiesta. In questo caso, fare clic su **Scadenza regola** per far scadere la regola.

| Nodo gerarchia dimensioni di elemento di costo | Nodo gerarchia dimensioni di oggetto di costo | Percentuale fissa | Importo fisso | Data di inizio validità | Data di fine validità  |
|---------------------------------------|--------------------------------------|------------------|--------------|------------|-----------|
| Costo fisso                            | Organizzazione                         | 100,00           | 0.00         | 1/1/2017   | Mai     |
| 10001                                 | Organizzazione                         | 0.00             | 150,00       | 1/1/2017   | Mai     |
| 10001                                 | Dati finanziari                              |                  | 50,00        | 1/1/2017   | 20/1/2017 |
| Comportamento costo o Costo variabile        | Organizzazione                         | 0.00             | 0.00         | 1/1/2017   | Mai     |

Tutti i calcoli dei costi generali eseguiti dopo il 20 gennaio 2017 non considerano più questa regola.

> [!NOTE] 
> I campi **Valida fino a** e **Valido da** hanno una data di validità e un'ora di validità. È possibile far scadere la regola ed eseguire lo stesso giorno un nuovo calcolo dei costi generali.

## <a name="define-dimension-hierarchies-for-security-setup"></a>Definire le gerarchie di dimensioni per l'impostazione sicurezza

I dati di contabilità industriale devono essere resi disponibili per tutti i dirigenti responsabili di un'unità gerarchica. Nella terminologia di contabilità industriale, un'unità gerarchica è rappresentata come un oggetto di costo o un set di oggetti di costo.

Potenzialmente, tutti i responsabili potranno accedere ai dati aziendali altamente riservati, ad esempio ricavi e guadagni. Di conseguenza, è importante impostare la sicurezza, in modo che i responsabili vedano solo i dati rilevanti. Per facilitare il controllo della sicurezza dei dati è necessario definire le gerarchie di dimensioni.

- L'utilizzo delle gerarchie di dimensioni viene applicato solo quando il valore di dimensione selezionato nel riferimento di gerarchia di dimensioni è una dimensione oggetto di costo.
- Solo una gerarchia di dimensioni può essere attivata per dimensione oggetto di costo nella gerarchia elenco accessi.

**Dettagli gerarchia dimensioni**

| Nome gerarchia dimensioni | Dimensione    | Nome tipo di gerarchia dimensioni      | Gerarchia elenco accessi |
|--------------------------|--------------|------------------------------------|-----------------------|
| Organizzazione             | Centri di costo | Gerarchia classificazioni dimensione | **Sì**               |

Una nuova scheda dettaglio **Utenti** è disponibile nella finestra di progettazione della gerarchia. È possibile inserire uno o più ID utente per ogni nodo della gerarchia.

|                 | Utenti            | Intervalli membro di dimensione   |                         |
|-----------------|------------------|---------------------------|-------------------------|
| **Nodi**       | **ID utente**      | **Membro di dimensione di inizio** | **Membro di dimensione di fine** |
| Organizzazione    | Benjamin, Claire |                           |                         |
| &nbsp;&nbsp;Amministratore         | aprile            |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Dati finanziari   | Alicia           | CC002                     | CC003                   |
|                 |                  | CC007                     | CC007                   |
| &nbsp;&nbsp;&nbsp;&nbsp;Risorse umane        | Arnie            | CC001                     | CC001                   |
| &nbsp;&nbsp;Produzione    | David            |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Imballaggio | Ellen            | CC005                     | CC005                   |
| &nbsp;&nbsp;&nbsp;&nbsp;Assemblaggio  | Chris            | CC006                     | CC006                   |

> [!NOTE] 
> I contabili devono essere assegnati al primo livello della gerarchia, in modo che possano visualizzare tutte le voci della contabilità industriale.

Per attivare la gerarchia elenco accessi e le relative impostazioni di sicurezza, passare a **Contabilità industriale** > **Impostazione** > **Parametri** > **Generale**. Selezionare il parametro **Abilita accesso in visualizzazione per membri di dimensione oggetto di costo**.

Le impostazioni per la gerarchia dell'elenco accessi vengono utilizzate per controllare i dati visualizzati nelle seguenti aree:

- Area di lavoro **Controllo costi** (client):

    - Data dei moduli utilizzati per eseguire il drill-down degli scenari

- Area di lavoro **Controllo costi** (applicazione mobile):

    - Saldi nelle schede

- Power BI:

    - Data visualizzati nelle visualizzazioni di Power BI
    - Le visualizzazioni dei dati di Power BI sono incorporate nel client Dynamics 365 Finance

> [!NOTE] 
> - Prima che la gerarchia dell'elenco accessi possa influire sui dati in Power BI, la gerarchia dell'elenco accessi e la sicurezza a livello di riga in Power BI devono essere abbinate. Per ulteriori informazioni, vedere [Impostare la sicurezza del pacchetto di contenuti per la contabilità industriale](../../dev-itpro/analytics/setup-security-cost-accounting-content-pack.md).
> - La gerarchia elenco accessi non rende sicura l'esportazione dei dati in Excel. Di conseguenza, lo strumento di creazione report dovrà essere utilizzato solo dai responsabili e dai contabili che devono avere l'accesso completo per visualizzare i dati.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]