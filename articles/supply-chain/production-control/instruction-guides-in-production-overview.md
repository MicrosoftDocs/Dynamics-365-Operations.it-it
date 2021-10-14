---
title: Fornire guide alla realtà mista per i lavoratori nei reparti di produzione
description: In questo argomento viene descritto come integrare il modulo di gestione della produzione in Microsoft Dynamics 365 Supply Chain Management con Dynamics 365 Guides.
author: johanhoffmann
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkGuidesManufacturing
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "61943"
- intro-internal
ms.assetid: a3847f07-fca4-4140-a26f-d83c6ac68dde
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.15
ms.openlocfilehash: edb4d1217617ee3bcb7f528da4aad42fb4fb6b82
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7576906"
---
# <a name="provide-mixed-reality-guides-for-workers-in-production"></a>Fornire guide alla realtà mista per i lavoratori nei reparti di produzione

[!include [banner](../includes/banner.md)]
[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

I lavoratori nei processi di produzione beneficeranno di istruzioni pertinenti fornite al momento giusto nel contesto del loro lavoro. Le *istruzioni* si applicano in diversi settori di lavoro, tra cui assembly, servizio, operazioni, certificazione e sicurezza. In tutte queste funzioni aziendali principali, le istruzioni di formazione continua possono aiutare i lavoratori a ottenere di più e lavorare meglio.

## <a name="introduction"></a>Introduzione

Puoi fornire istruzioni in diversi modi. Un sistema efficiente e pronto all'uso utilizza [Dynamics 365 Guides](https://dynamics.microsoft.com/mixed-reality/guides/).

Dynamics 365 Guides può aiutare i dipendenti con l'apprendimento pratico. Puoi definire processi standardizzati con istruzioni dettagliate che guidano i dipendenti alla scoperta di strumenti e parti di cui hanno bisogno e mostrano ai dipendenti il modo in cui utilizzare questi strumenti in situazioni di lavoro reali.

Puoi associare guide a vari aspetti del controllo della produzione, tra cui:

- [Risorse](#resources)
- [Gruppi di risorse](#resource-groups)
- [Prodotti rilasciati](#released-products)
- [Formule](#formulas)
- [Versioni formula](#formula-versions)
- [Distinte base (DBA)](#bom)
- [Versioni DBA](#bom-versions)
- [Cicli di lavorazione](#routes)
- [Versioni cicli di lavorazione](#route-versions)
- [Relazioni operative di cicli di lavorazione](#route-operation-relations)

> [!NOTE]
> Puoi anche associare delle guide a Gestione cespiti. Per ulteriori informazioni su quell'opzione, vedi [Integrare Dynamics 365 Supply Chain Management (Gestione cespiti) con Dynamics 365 Guides](../asset-management/asset-management-guides-integration.md).

Quando un lavoratore di prima linea sceglie un processo nell'officina tramite Supply Chain Management, il lavoratore può vedere [le guide pertinenti](#logic) nella scheda del processo. Quando il lavoratore sceglie una guida specifica, sullo schermo viene visualizzato un codice a matrice per quella guida. Il lavoratore quindi usa HoloLens per eseguire la scansione del codice a matrice, che avvia le guide e mostra le istruzioni richieste.

Le sottosezioni seguenti descrivono alcuni scenari selezionati in cui le aziende di tutti i settori possono vedere il valore maggiore quando utilizzano guide per presentare istruzioni per la produzione.

### <a name="assembly"></a>Assembly

![Utilizzare guide per le attività di assembly.](media/instruction-guides-hero-assembly.png "Utilizzare guide per le attività di servizio")

Le istruzioni nelle operazioni di assemblaggio mostrano ai lavoratori gli strumenti e le parti di cui hanno bisogno e come utilizzarli nelle situazioni di lavoro reali.

I responsabili della produzione possono creare e assegnare guide, ad esempio, per [cicli di lavorazione di produzione](routes-operations.md),[ relazioni operative](routes-operations.md#operation-relations) o [distinte base](bill-of-material-bom.md). I lavoratori troveranno le istruzioni pertinenti nelle rispettiva esperienza operativa nell'officina.

### <a name="service"></a>Gestione assistenza

![Utilizzare guide per le attività di servizio.](media/instruction-guides-hero-service.png "Utilizzare guide per le attività di servizio")

Fornire ai tecnici istruzioni guidate sul sito, eliminando la necessità di programmare visite aggiuntive.

I responsabili dei servizi possono assegnare guide, ad esempio a specifici [prodotti](../../commerce/product.md) che seguono routine di valutazione della qualità.

### <a name="quality"></a>Qualità

![Utilizzare guide per le attività di controllo qualità.](media/instruction-guides-hero-quality.png "Utilizzare guide per le attività di controllo qualità")

Implementa nuovi processi e garantisci una maggiore coerenza trasformando la conoscenza dei dipendenti in uno strumento ripetibile.

I responsabili del controllo qualità possono assegnare guide, ad esempio a [prodotti](../../commerce/product.md) che seguono routine di valutazione della qualità.

### <a name="certifications"></a>Certificazioni

![Utilizzare guide per le attività di certificazione.](media/instruction-guides-hero-certification.png "Utilizzare guide per attività di certificazione")

Assicurati che ogni dipendente soddisfi standard elevati identificando rapidamente chi ha bisogno di supporto e dove.

### <a name="safety"></a>Sicurezza

![Utilizzare guide per istruzioni relative alla sicurezza sul lavoro.](media/instruction-guides-hero-safety.png "Utilizzare guide per istruzioni relative alla sicurezza sul lavoro")

Fornisci istruzioni che percorrono virtualmente le procedure pericolose prima di eseguirle nell'ambiente fisico. Con un approccio di realtà mista, i lavoratori possono sperimentare procedure pericolose virtualmente.

I responsabili della produzione possono fornire istruzioni di movimentazione dedicate per procedure di gestione di materiali pericolosi o delicate assegnando istruzioni a [articoli prodotto](../../commerce/product.md),[cicli di lavorazione](routes-operations.md) e [ operazioni](routes-operations.md#operation-relations).

## <a name="get-started-with-instructions-and-guides"></a>Iniziare con istruzioni e guide

Per abilitare le istruzioni nei processi di produzione, Supply Chain Management fornisce un'integrazione predefinita con Dynamics 365 Guides. Per creare, gestire e assegnare istruzioni di realtà mista a risorse di produzione e a operazioni lavorative, è necessaria un'istanza con licenza e installata di Guides.

### <a name="prerequisites"></a>Prerequisiti

Per utilizzare questa funzionalità, il sistema deve includere quanto segue:

- Dynamics 365 Supply Chain Management 10.0.15 o versione successiva
- [Doppia scrittura](../../fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write.md) per le app Supply Chain Management.
- [Dynamics 365 Guides](/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) versione 400.0.1.48 o successiva

### <a name="turn-on-the-feature"></a>Attivare la funzionalità

Per rendere disponibile la funzionalità nel sistema, devi abilitare le relative chiavi di configurazione. Hai bisogno di effettuare questa operazione una sola volta. A tale scopo, un amministratore deve:

1. Mettere il sistema in modalità di manutenzione come descritto in [Modalità di manutenzione](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Accedere a **Amministrazione sistema \> Imposta \> Configurazione licenza**.
1. Espandere la sezione **Realtà mista** e quindi selezionare la casella di controllo **Guida alla realtà mista**.
1. Espandere la sezione **Gestione produzione** e quindi selezionare la casella di controllo **Istruzioni produzione**.
1. Disattivare la modalità di manutenzione come descritto in [Modalità di manutenzione](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
  
## <a name="configure-how-guides-appear-on-the-shop-floor"></a>Configurare la modalità di visualizzazione delle guide nell'officina

Per configurare la modalità di visualizzazione delle guide nell'officina, vai a **Realtà mista \> Dynamics 365 Guides \> Configura integrazione delle guide**.

![Configurare l'integrazione delle guide per la produzione.](media/instruction-guides-configure-integration.png "Configurare l'integrazione delle guide per la produzione")

Impostare i seguenti campi:

- **URL Microsoft Dataverse** - Specifica l'URL per l'ambiente Microsoft Dataverse in cui vengono create le Guides. Il formato è "contoso.crm4.dynamics.com", dove la prima parte dell'URL è in genere denominata in base all'organizzazione (ad esempio "contoso."), la seconda parte è specifica dell'area dati dell'ambiente (ad esempio "crm4") e l'ultima parte è il dominio (come "dynamics.com"). Un modo per trovare l'URL corretto è andare a [home.dynamics.com](https://home.dynamics.com/) e quindi aprire l'app Guides. Quando si apre Guides, l'URL è visualizzato nella barra degli indirizzi del browser (prendere solo l'URL di base, che dovrebbe assomigliare all'esempio precedente). Questo valore viene utilizzato per comporre gli indirizzi per le guide e verrà codificato nei codici a matrice.
- **Dimensione codice a matrice** - Imposta la dimensione del codice a matrice di cui viene eseguito il rendering. Ti consigliamo di scegliere una dimensione che riempia la maggior parte dello schermo, ma non di più. *15* è in genere un buon valore.
- **Livello di correzione errori codice a matrice** - Imposta la granularità del codice a matrice. Una granularità più elevata può aumentare l'affidabilità del codice, ma il valore di **Dimensione codice a matrice** deve essere abbastanza grande da supportare il livello di dettaglio richiesto dal livello di correzione selezionato.

> [!TIP]
> - I codici a matrice di dimensioni troppo grandi per lo schermo verranno visualizzati più lentamente e quindi ridotti per adattarsi allo schermo. Non forniscono alcun vantaggio.
> - I codici a matrice troppo piccoli possono ridurre la capacità di HoloLens di leggere correttamente il codice in alcuni ambienti.
> - Ti consigliamo di testare le impostazioni di ogni dispositivo in cui verranno visualizzati i codici a matrice per utenti HoloLens. Scegli impostazioni che forniscono una leggibilità sufficiente nell'officina.  

## <a name="get-an-overview-of-all-guide-assignments"></a>Ottenere una panoramica di tutti le assegnazioni delle guide

Usa la pagina **Tutte le guide** per visualizzare l'elenco di tutte le guide disponibili nell'organizzazione e tutte le assegnazioni a processi e risorse di produzione. Per aprirla, vai a **Realtà mista\> Guide \> Tutte le guide**. L'elenco in alto mostra tutte le guide disponibili e puoi utilizzare il campo qui per filtrare l'elenco. L'elenco in basso mostra tutte le assegnazioni delle guida e fornisce una barra degli strumenti per gestirle.

![Gestire le guide.](media/instruction-guides-allguides.png "Gestire le guide")

Le sezioni seguenti descrivono i tipi di oggetti a cui è possibile assegnare le guide. Ogni guida assegnata fornisce istruzioni che vengono automaticamente associate ai rispettivi processi di produzione e saranno disponibili nell'officina.

## <a name="associate-a-guide-to-a-resource"></a><a name="resources"></a>Associare una guida a una risorsa

Aggiungi una guida a una [risorsa](operations-resources.md) per rendere disponibile la guida nel contesto dei processi di produzione pertinenti.

### <a name="typical-scenario-using-resources"></a>Scenario tipico che utilizza risorse

Ad esempio, potresti associare una guida con istruzioni generali di sicurezza o di gestione di una macchina a una risorsa di tipo macchina. La guida sarà quindi disponibile per ogni processo eseguito sulla macchina.

### <a name="add-a-guide-to-a-resource"></a>Aggiungere una guida a una risorsa

Per aggiungere una guida a una risorsa:

1. Vai a **Controllo produzione \> Impostazioni \> Risorse \> Risorse**.
1. Nel riquadro dell'elenco, seleziona la risorsa a cui desideri assegnare una guida.
1. Espandi la Scheda dettaglio **Guide associate**.
1. Seleziona **Aggiungi** nella barra degli strumenti **Guide associate**. Una nuova riga viene aggiunta alla griglia.
1. Per la nuova riga, utilizza l'elenco a discesa nella colonna **Nome** per scegliere la guida che desideri assegnare. Se disponi di un numero elevato di guide, puoi filtrare l'elenco per trovare quella che stai cercando.
    ![Gestire le guide.](media/instruction-guides-allguides.png "Gestire le guide")

## <a name="associate-a-guide-to-a-resource-group"></a><a name="resource-groups"></a>Associare una guida a un gruppo di risorse

Puoi aggiungere una guida a [gruppi di risorse](tasks/define-discrete-manufacturing-resource-group.md) se la utilizzi per gestire gruppi di macchine, linee di produzione o celle di lavoro.

### <a name="typical-scenarios-using-resource-groups"></a>Scenari tipici che utilizzano gruppi di risorse

**Esempio 1:** hai definito un gruppo di risorse per diverse macchine dello stesso modello. Anziché assegnare la guida di istruzioni di gestione appropriata per il modello di macchina a ogni risorsa pertinente, puoi assegnare la guida al gruppo di risorse che riflette quel modello di macchina.

**Esempio 2:** hai definito un gruppo di risorse per una cella di lavoro che contiene diverse macchine e disponi di una guida con istruzioni generali su come gestire la cella di lavoro. La guida si applica a qualsiasi attività di produzione in quella cella di lavoro.

### <a name="add-a-guide-to-a-resource-group"></a>Aggiungere una guida a un gruppo di risorse

Per aggiungere una guida a un gruppo di risorse:

1. Vai a **Controllo produzione \> Impostazioni \> Risorse \> Gruppi di risorse**.
1. Nel riquadro dell'elenco, seleziona il gruppo di risorse a cui desideri assegnare una guida.
1. Espandi la Scheda dettaglio **Guide associate**.
1. Seleziona **Aggiungi** nella barra degli strumenti **Guide associate**. Una nuova riga viene aggiunta alla griglia.
1. Per la nuova riga, utilizza l'elenco a discesa nella colonna **Nome** per scegliere la guida che desideri assegnare. Se disponi di un numero elevato di guide, puoi filtrare l'elenco per trovare quella che stai cercando.
    ![Aggiungere una guida a un gruppo di risorse.](media/instruction-guides-resourcegroup.png "Aggiungere una guida a un gruppo di risorse")

## <a name="associate-a-guide-to-a-released-product"></a><a name="released-products"></a>Associare una guida a un prodotto rilasciato

Puoi aggiungere una guida a qualsiasi [prodotto rilasciato](../pim/tasks/create-released-product-single-company.md).

### <a name="typical-scenario-using-released-products"></a>Scenario tipico che utilizza prodotti rilasciati

Le guide a livello di prodotto aiutano i lavoratori in officina con istruzioni relative al funzionamento o alla gestione di uno specifico prodotto o articolo rilasciato.

### <a name="add-a-guide-to-a-released-product"></a>Aggiungere una guida a un prodotto rilasciato

Per aggiungere una guida a un prodotto rilasciato:

1. Vai a **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
1. Apri il prodotto a cui desideri assegnare una guida.
1. Nel riquadro azioni, apri la scheda **Progettazione** e, nel gruppo **Visualizza**, seleziona **Guide associate**.
1. Viene aperta la pagina **Guide associate** per il prodotto selezionato.
1. Seleziona **Aggiungi** per aggiungere una nuova riga alla griglia. 
1. Per la nuova riga, utilizza l'elenco a discesa nella colonna **Nome** per scegliere la guida che desideri assegnare.
    ![Aggiungere una guida a un prodotto rilasciato.](media/instruction-guides-ReleasedProduct-AddGuides.png "Aggiungere una guida a un prodotto rilasciato")

## <a name="associate-a-guide-to-a-formula"></a><a name="formulas"></a>Associare una guida a una formula

Puoi aggiungere una guida a qualsiasi [formula](bill-of-material-bom.md#formulas-co-products-and-by-products).

### <a name="typical-scenario-using-formulas"></a>Scenario tipico che utilizza formule
  
Le guide a livello di formula forniscono agli addetti all'officina istruzioni di gestione guidate nel contesto di una formula o ricetta. Le guide possono anche essere assegnate alle versioni di una formula.

> [!NOTE]
> Puoi assegnare linee guida pertinenti per i processi di produzione basati su una formula a un ciclo di lavorazione, una versione di un ciclo di lavorazione o relazioni operative di ciclo di lavorazione.  

> Al momento le guide non possono essere associate a singole righe di formula.

### <a name="add-a-guide-to-a-formula"></a>Aggiungere una guida a una formula

Per aggiungere una guida a una formula:

1. Vai a **Gestione informazioni sul prodotto \> Distinte base e formule \> Formule**.
1. Apri la formula a cui desideri assegnare una guida.
1. Apri la scheda **Intestazione** sopra la Scheda dettaglio superiore.
1. Espandi la Scheda dettaglio **Guide associate**.
1. Seleziona **Aggiungi** nella barra degli strumenti **Guide associate**. Una nuova riga viene aggiunta alla griglia.
1. Per la nuova riga, utilizza l'elenco a discesa nella colonna **Nome** per scegliere la guida che desideri assegnare.
    ![Aggiungere una guida a una formula.](media/instruction-guides-Formula.png "Aggiungere una guida a una formula")

## <a name="associate-a-guide-to-a-formula-version"></a><a name="formula-versions"></a>Associare una guida a una versione di formula

Puoi aggiungere una guida a qualsiasi [versione di formula](bill-of-material-bom.md#bom-and-formula-versions).

### <a name="typical-scenario-using-formula-versions"></a>Scenario tipico che utilizza versioni di formula

Le guide associate a una versione di una formula forniscono ai lavoratori nell'officina istruzioni che illustrano la produzione di quella versione della ricetta della formula.

> [!TIP]
> Puoi assegnare linee guida pertinenti per i processi di produzione basati su questa versione di formula a un ciclo di lavorazione, una versione di un ciclo di lavorazione o relazioni operative di ciclo di lavorazione.  

> [!NOTE]
> Al momento le guide non possono essere associate a singole righe di formula.

### <a name="add-a-guide-to-a-formula-version"></a>Aggiungere una guida a una versione di formula

Per aggiungere una guida a una versione di formula:

1. Vai a **Gestione informazioni sul prodotto \> Distinte base e formule \> Formule**.
1. Apri la formula che include una versione a cui desideri assegnare una guida.
1. Apri la scheda **Intestazione** sopra la Scheda dettaglio superiore.
1. Nella Scheda dettaglio **Versioni formula**, seleziona la versione a cui si desidera assegnare una guida.
1. Nella barra degli strumenti **Versioni formula**, seleziona **Guide associate**.
    ![Aprire le guide associate a una versione di formula selezionata.](media/instruction-guides-FormulaVersion.png "Aprire le guide associate a una versione di formula selezionata")
1. Viene aperta la pagina **Guide associate** per la versione di formula.
1. Seleziona **Aggiungi** per aggiungere una nuova riga alla griglia. 
1. Per la nuova riga, utilizza l'elenco a discesa nella colonna **Nome** per scegliere la guida che desideri assegnare.
    ![Aggiungere una guida a una versione di formula.](media/instruction-guides-FormulaVersionAddGuide.png "Aggiungere una guida a una versione di formula")

## <a name="associate-a-guide-to-a-bill-of-materials"></a><a name="bom"></a>Associare una guida a una distinta base

Puoi aggiungere una guida a qualsiasi [distinta base](bill-of-material-bom.md) (DBA).

### <a name="typical-scenario-using-bills-of-materials"></a>Scenario tipico utilizzando distinte base

Le guide associate a una distinta materiali forniscono ai lavoratori nell'officina le istruzioni che spiegano come preparare e gestire il materiale di distinta materiali. Le guide possono anche essere assegnate a versioni di una distinta materiali.

> [!NOTE]
> Al momento le guide non possono essere associate a singole righe di distinta materiali.

### <a name="add-a-guide-to-a-bill-of-materials"></a>Aggiungere una guida a una distinta base

Per aggiungere una guida a una distinta base:

1. Vai a **Gestione informazioni sul prodotto \> Distinte base e formule \> Distinte base**.
1. Apri la distinta base a cui desideri assegnare una guida.
1. Apri la scheda **Intestazione** sopra la Scheda dettaglio superiore.
1. Espandi la Scheda dettaglio **Guide associate**.
1. Seleziona **Aggiungi** nella barra degli strumenti **Guide associate**. Una nuova riga viene aggiunta alla griglia.
1. Per la nuova riga, utilizza l'elenco a discesa nella colonna **Nome** per scegliere la guida che desideri assegnare.
    ![Aggiungere una guida a una distinta materiali.](media/instruction-guides-BOM.png "Aggiungere una guida a una distinta materiali")

## <a name="associate-a-guide-to-a-bill-of-materials-version"></a><a name="bom-versions"></a>Associare una guida a una versione di distinta base

Puoi aggiungere una guida a qualsiasi [versione di distinta base](bill-of-material-bom.md#bom-and-formula-versions).

### <a name="typical-scenario-using-bill-of-materials-versions"></a>Scenario tipico che utilizza versioni di distinta base

Le guide associate a una singola versione di distinta materiali forniscono ai lavoratori nell'officina istruzioni che spiegano come preparare e gestire il materiale per una versione di una distinta materiali diversa dalla distinta base generica o da altre versioni della stessa.

> [!NOTE]
> Al momento le guide non possono essere associate a singole righe di distinta materiali.

### <a name="add-a-guide-to-a-bill-of-materials-version"></a>Aggiungere una guida a una versione di distinta materiali

Per aggiungere una guida a una versione di distinta materiali:

1. Vai a **Gestione informazioni sul prodotto \> Distinte base e formule \> Distinte base**.
1. Apri la distinta materiali che include una versione a cui desideri assegnare una guida.
1. Apri la scheda **Intestazione** sopra la Scheda dettaglio superiore.
1. Nella Scheda dettaglio **Versioni DBA**, seleziona la versione a cui desideri assegnare una guida.
1. Nella barra degli strumenti **Versioni DBA**, seleziona **Guide associate**.
    ![Aprire le guide associate a una versione di DBA selezionata.](media/instruction-guides-BOMVersion.png "Aprire le guide associate a una versione di DBA selezionata")
1. Viene aperta la pagina **Guide associate** per la versione di DBA.
1. Seleziona **Aggiungi** per aggiungere una nuova riga alla griglia.
1. Per la nuova riga, utilizza l'elenco a discesa nella colonna **Nome** per scegliere la guida che desideri assegnare.
    ![Aggiungere una guida a una versione di DBA.](media/instruction-guides-BOMVersionAddGuide.png "Aggiungere una guida a una versione di DBA")

## <a name="associate-a-guide-to-a-route"></a><a name="routes"></a>Associare una guida a un ciclo di lavorazione

Puoi aggiungere una guida a qualsiasi [ciclo di lavorazione](routes-operations.md).

### <a name="typical-scenario-using-routes"></a>Scenario tipico che utilizza cicli di lavorazione

I cicli di lavorazione vengono generalmente utilizzati per specificare il modo in cui un determinato prodotto rilasciato deve essere prodotto in base a una DBA o una versione di DBA e con un insieme di risorse o gruppi di risorse.

Assegna una guida a un ciclo di lavorazione per fornire istruzioni dettagliate per il rispettivo processo di produzione.

### <a name="add-a-guide-to-a-route"></a>Aggiungere una guida a un ciclo di lavorazione

Per aggiungere una guida a un ciclo di lavorazione:

1. Vai a **Controllo produzione \> Tutti i cicli di lavorazione**.
1. Apri il ciclo di lavorazione a cui desideri assegnare una guida.
1. Espandi la Scheda dettaglio **Guide associate**.
1. Seleziona **Aggiungi** nella barra degli strumenti **Guide associate**. Una nuova riga viene aggiunta alla griglia.
1. Per la nuova riga, utilizza l'elenco a discesa nella colonna **Nome** per scegliere la guida che desideri assegnare.
    ![Aggiungere una guida a un ciclo di lavorazione.](media/instruction-guides-Route.png "Aggiungere una guida a un ciclo di lavorazione")

## <a name="associate-a-guide-to-a-route-version"></a><a name="route-versions"></a>Associare una guida a una versione di ciclo di lavorazione

Puoi aggiungere una guida a qualsiasi [versione di ciclo di lavorazione](routes-operations.md#route-versions).

### <a name="typical-scenario-using-route-versions"></a>Scenario tipico che utilizza versioni di ciclo di lavorazione

Le versioni di ciclo di lavorazione sono in genere utilizzate per specificare varianti dei processi di produzione in base a un ciclo di lavorazione esistente. Puoi assegnare guide differenti a ciascuna versione di ciclo di lavorazione.

### <a name="add-a-guide-to-a-route-version"></a>Aggiungere una guida a una versione di ciclo di lavorazione

Per aggiungere una guida a una versione di ciclo di lavorazione:

1. Vai a **Controllo produzione \> Tutti i cicli di lavorazione**.
1. Apri il ciclo di lavorazione a cui desideri assegnare una guida.
1. Nella Scheda dettaglio **Versioni**, seleziona la versione a cui desideri assegnare una guida.
1. Nella barra degli strumenti **Versioni**, seleziona **Guide associate**.
    ![Aprire le guide associate a una versione di ciclo di lavorazione selezionata.](media/instruction-guides-RouteVersion.png "Aprire le guide associate a una versione di ciclo di lavorazione selezionata")
1. Viene aperta la pagina **Guide associate** per la versione di DBA.
1. Seleziona **Aggiungi** per aggiungere una nuova riga alla griglia.
1. Per la nuova riga, utilizza l'elenco a discesa nella colonna **Nome** per scegliere la guida che desideri assegnare.
    ![Aggiungere una guida a una versione di ciclo di lavorazione.](media/instruction-guides-RouteVersionAddGuide.png "Aggiungere una guida a una versione di ciclo di lavorazione")

## <a name="associate-a-guide-to-a-route-operation-relation"></a><a name="route-operation-relations"></a>Associare una guida a una relazione operativa di ciclo di lavorazione

Puoi aggiungere una guida a qualsiasi [relazione operativa di ciclo di lavorazione](routes-operations.md#operation-relations).

### <a name="typical-scenario-using-route-operation-relations"></a>Scenario tipico che utilizza relazioni operative di ciclo di lavorazione

Le relazioni operative sono il modo più specifico di aggiungere linee guida a un processo di prodotto e alle operazioni correlate. Puoi specificare linee guida per ciascuna operazione di un ciclo di lavorazione e specificare linee guida differenti per qualsiasi tipo di contesto di relazione specificato per un ciclo di lavorazione, ad esempio per elementi specifici, configurazioni e altro. Puoi anche specificare a quali fasi dell'operazione si applicano le linee guida (come configurazione, messa in coda, elaborazione o trasporto).

> [!NOTE]
> Se specifichi guide per diverse relazioni operative di un ciclo di lavorazione, tra quelle guide, solo la guida della relazione più specifica verrà visualizzata nell'officina per il processo generato.

### <a name="add-a-guide-to-a-route-operation-relation"></a>Aggiungere una guida a una relazione operativa di ciclo di lavorazione

Per aggiungere una guida a una relazione operativa di ciclo di lavorazione:

1. Vai a **Controllo produzione \> Tutti i cicli di lavorazione**.
1. Apri il ciclo di lavorazione a cui desideri assegnare una guida.
1. Nel riquadro azioni, apri la scheda **Ciclo di lavorazione** e, nel gruppo **Gestisci**, seleziona **Dettagli ciclo di lavorazione**.
1. Viene aperta la pagina **Dettagli ciclo di lavorazione** per il ciclo di lavorazione selezionato.
1. Nella griglia in alto, seleziona l'operazione per cui desideri fornire linee guida.
1. Nella griglia inferiore, seleziona una relazione specifica (o la relazione **Tutto** generica).
    ![Selezionare un'operazione e quindi una relazione.](media/instruction-guides-RouteOperationRelation.png "Selezionare un'operazione e quindi una relazione")
1. Sopra la griglia inferiore, aprire la scheda **Guide associate**. ![Scheda Guide associate.](media/instruction-guides-RouteOperationRelation-AddGuide.png "Scheda Guide associate")
1. Seleziona **Aggiungi** nella barra degli strumenti nella parte superiore della griglia in basso per aggiungere una nuova linea alla griglia.
1. Per la nuova riga, utilizza l'elenco a discesa nella colonna **Nome** per scegliere la guida che desideri assegnare. Nel resto della riga, seleziona la casella di controllo di ogni contesto in cui la guida selezionata deve essere disponibile.

> [!NOTE]
> Puoi aggiungere una o più guide per ogni fase di ciascuna operazione.

## <a name="select-guides-from-the-shop-floor-execution-interface"></a>Selezionare le guide nell'interfaccia di esecuzione nell'officina

Quando un lavoratore apre un elenco di processi nell'interfaccia di esecuzione nell'officina, Supply Chain Management trova le guide pertinenti per i processi visualizzati. Usa il pulsante **Guide** per visualizzare le guide pertinenti.

![Pulsante Guide nell'interfaccia di esecuzione nell'officina.](media/instruction-guides-Shopfloor1.png "Pulsante Guide nell'interfaccia di esecuzione nell'officina")

Quindi indossare un HoloLens e accedere alla guida rispettiva dando uno sguardo al codice a matrice e attivando la rispettiva guida.

![Codice a matrice per accedere alle guide utilizzando un HoloLens.](media/instruction-guides-Shopfloor2.png "Codice a matrice per accedere alle guide utilizzando un HoloLens")

## <a name="resolving-the-logic-for-selecting-guides"></a><a name="logic"></a>Risoluzione della logica per la selezione delle guide

Puoi aggiungere guide ai seguenti dati di produzione:

- [Risorse](#resources)
- [Gruppi di risorse](#resource-groups)
- [Prodotti rilasciati](#released-products)
- [Formule](#formulas)
- [Versioni formula](#formula-versions)
- [Distinte base (DBA)](#bom)
- [Versioni DBA](#bom-versions)
- [Itinerari](#routes)
- [Versioni cicli di lavorazione](#route-versions)
- [Relazioni operative di cicli di lavorazione](#route-operation-relations)

Quando Supply Chain Management genera i processi per il reparto di produzione, raccoglierà le guide pertinenti da tali origini. Prendi nota delle regole importanti seguenti.

- Se associ una versione di DBA o di formula a un ciclo di lavorazione o ordine di produzione, per il processo verranno mostrate tutte le guide associate a quella versione e anche le guide associate alla distinta base o alla formula padre di quella versione.
- Se associ una versione di ciclo di lavorazione a un ordine di produzione, per il processo verranno mostrate tutte le guide associate a quella versione e anche le guide associate al ciclo di lavorazione padre di quella versione.
- Se definisci varie relazioni operative di ciclo di lavorazione che includono la relazione *Tutti* e vi assegni guide, per il processo verranno mostrate solo le guide della relazione più specifica.  

![Diagramma sulla risoluzione delle guide pertinenti.](media/instruction-guides-Resolve.png "Diagramma sulla risoluzione delle guide pertinenti")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]