---
title: Gestione modifiche di progettazione - Domande frequenti
description: Questo argomento fornisce risposte alle domande frequenti sulla funzionalitò di gestione delle modifiche di progettazione.
author: t-benebo
ms.date: 03/25/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-03-25
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: ba489358ef2d74e816186f29956aea5538a2432825c7d949e7c9cc23d947b997
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6714380"
---
# <a name="engineering-change-management-faq"></a>Gestione modifiche di progettazione - Domande frequenti

[!include [banner](../includes/banner.md)]

Questo argomento fornisce risposte alle domande frequenti sulla funzionalitò di gestione delle modifiche di progettazione.

## <a name="should-i-track-the-version-in-transactions"></a>Devo tenere traccia della versione nelle transazioni?

Quando crei una categoria di modifiche di progettazione, la pagina **Dettagli categoria modifiche di progettazione** fornisce un'opzione denominata **Tenere traccia delle versioni nelle transazioni**. Cos'è questa impostazione e cosa fa?

- Se imposti **Tenere traccia delle versioni nelle transazioni** su *Sì*, il campo **Gruppo di dimensioni** verrà filtrato in modo da mostrare solo i gruppi di dimensioni in cui la versione è una dimensione attiva.
- Se imposti **Tenere traccia delle versioni nelle transazioni** su *No*, il campo **Gruppo di dimensioni** verrà filtrato in modo da mostrare solo i gruppi di dimensioni in cui la dimensione della versione **non** è una dimensione attiva.

### <a name="if-you-track-the-version-in-transactions"></a>Se tieni traccia della versione nelle transazioni

Per le categorie di progettazione in cui è stato selezionato un gruppo di dimensioni in cui la versione è una dimensione attiva, si terrà traccia delle versioni nelle transazioni per i prodotti in quella categoria. In questo caso, il prodotto di progettazione sarà una rappresentazione generale prodotto e ogni versione del prodotto sarà una variante prodotto che utilizza la dimensione della versione. Altre dimensioni possono essere utilizzate insieme alla dimensione della versione.

In questo caso, ogni versione di progettazione verrà considerata come una variante in tutti i processi. Pertanto, se si dispone di una variante specifica in una transazione (in modo da poter determinare quale variante è stata venduta o acquistata), è necessario gestire lo stock per ciascuna versione, la pianificazione generale pianificherà la fornitura per ciascuna versione e così via. Se si ritira una versione dal mercato, è necessario regolare manualmente le date di inizio e fine validità in modo che riflettano la modifica. Devi anche gestire il tuo inventario per assicurarti di non avere versioni inutilizzate degli articoli nei tuoi magazzini.

Sebbene questa opzione richieda uno sforzo di gestione maggiore, la consigliamo se si richiede un'elevata tracciabilità delle versioni specifiche utilizzate in ciascuna transazione.

### <a name="if-you-dont-track-the-version-in-transactions"></a>Se non tieni traccia della versione nelle transazioni

Per le categorie di progettazione in cui è stato selezionato un gruppo di dimensioni in cui la versione **non** è una dimensione attiva, **non** si terrà traccia delle versioni nelle transazioni per i prodotti in quella categoria. In questo caso, se non utilizzi nessun'altra dimensione, il prodotto di progettazione sarà un prodotto specifico. Il prodotto sarà comunque dotato di versione ed è possibile gestire le informazioni su versioni specifiche (ad esempio, la loro distinta base \[DBA] e ciclo di lavorazione), ma non sarai in grado di tracciare quale versione specifica è stata utilizzata in ciascuna transazione. Le date di inizio e fine validità indicano la validità di ciascuna versione.

Questa opzione è molto più semplice da gestire, perché se si desidera passare da una versione all'altra, è sufficiente apportare le modifiche richieste in un ordine di modifica, quindi aggiornare le date di inizio e fine validità nella versione di progettazione. I processi di produzione preleveranno quindi la distinta base e il ciclo di lavorazione richiesti per il prodotto (e la sua versione specifica).

La maggior parte delle organizzazioni sceglie questa opzione perché fornisce la gestione delle versioni e delle modifiche, ma non aggiunge il sovraccarico aggiuntivo di tenere traccia della versione in ogni transazione, nell'inventario e durante la pianificazione generale.

## <a name="which-fields-are-copied-from-the-released-item-template"></a>Quali campi vengono copiati dal modello di articolo rilasciato?

Quando una società di progettazione crea un prodotto di progettazione, quel prodotto viene creato come prodotto rilasciato nella società di progettazione. Il prodotto rilasciato che viene creato è basato sul *modello di articolo rilasciato* selezionato. (Il modello di articolo rilasciato è esso stesso un prodotto rilasciato esistente.) Il modello di articolo rilasciato viene utilizzato anche quando il prodotto viene rilasciato a una società operativa. In ogni caso, il modello di articolo rilasciato definisce la maggior parte dei valori di campo per il prodotto rilasciato e tali valori provengono dalla pagina **Dettagli prodotto rilasciato** associata.

Le seguenti tabelle mostrano i campi che vengono copiati durante questi processi.

| Scheda dettaglio | Campi che vengono copiati durante la creazione del prodotto nella società di progettazione | Campi che vengono copiati al momento del rilascio a una società operativa |
|---|---|---|
| **Generali** | Tutti i campi nella sezione **Amministrazione** | Gli stessi campi che vengono copiati per la società di progettazione |
| **Acquisti** | Tutti i campi | Tutti i campi tranne **Unità** |
| **Vendi** | Tutti i campi nelle seguenti sezioni: **Ordine cliente**, **Amministrazione**, **Tassazione**, **Aggiornamento prezzi**, **Prezzo vendita di base**, **Addebiti**, **Sconti**, e **Prodotto alternativo** | Tutti Gli stessi campi che vengono copiati per la società di progettazione, tranne **Unità** |
| **Commercio estero** | Tutti i campi | Tutti i campi |
| **Gestione articoli** | Tutti i campi e le sezioni *tranne* **Dimensioni fisiche** e **Peso variabile** | Tutti Gli stessi campi che vengono copiati per la società di progettazione, tranne **Unità** |
| **Progetta**, **Pianifica**, **Gestisci i costi**, **Gestisci progetti**, **Dimensioni finanziarie**, e **Magazzino** | Tutti i campi | Tutti i campi tranne **Unità DBA** |
| **Varianti prodotto** | Tutti i campi nella sezione **Variante prodotto predefinita** | Gli stessi campi che vengono copiati per la società di progettazione |

Oltre ai campi mostrati nella tabella precedente, tutte le impostazioni dell'ordine predefinite vengono copiate dal modello di articolo rilasciato, sia quando il prodotto viene creato nella società di progettazione sia quando viene rilasciato a una società operativa. (Per visualizzare le impostazioni dell'ordine predefinite per un modello di articolo rilasciato, aprire la pagina **Dettagli prodotto rilasciato** pertinente, quindi, nel riquadro azioni, nella scheda **Gestione articoli**, selezionare **Impostazioni ordine predefinite**.)

## <a name="should-i-create-a-separate-legal-entity-for-engineering-products-or-use-an-existing-legal-entity"></a>Devo creare una persona giuridica separata per i prodotti di progettazione o utilizzare una persona giuridica esistente?

I requisiti aziendali determinano se è necessario creare una nuova persona giuridica per i prodotti di progettazione.

Creando una società di progettazione separata, è possibile mantenere separati i dati di progettazione e quindi aggiungere le modifiche in base alle esigenze per le società operative locali. In questo modo, puoi ottenere gli obiettivi seguenti:

- Mantenere un'entità separata in cui vengono creati e gestiti i prodotti di progettazione.
- Impedire ai prodotti di progettazione di apparire insieme al resto dei tuoi prodotti rilasciati fino a quando non sono pronti e rilasciati.
- Distinguere chiaramente i dati dettati dalla progettazione dai dati locali.

D'altra parte, dovresti probabilmente utilizzare una persona giuridica esistente come società di progettazione se le seguenti condizioni si applicano:

- Hai una sola persona giuridica nel tuo sistema e/o non hai bisogno di una netta separazione tra i prodotti che vengono progettati.
- Non vuoi duplicare alcuni dati, come gruppi di risorse, risorse, operazioni e (forse) siti.

## <a name="what-is-the-nomenclature-for-engineering-versions-and-variants"></a>Qual è la nomenclatura per le versioni e le varianti di progettazione?

La nomenclatura per i prodotti  e le varianti di prodotto di progettazione funziona nel modo seguente:

- Per il prodotto di progettazione (ovvero, il prodotto specifico se non vengono utilizzate dimensioni o la rappresentazione generale prodotto se viene utilizzata una dimensione), la nomenclatura della regola numerica è definita nella categoria del prodotto di progettazione. Qui hai la possibilità di utilizzare una sequenza numerica, costanti di testo e nomi e valori di attributi.
- Per ogni variante di un prodotto di progettazione (se il prodotto di progettazione è una rappresentazione generale prodotto, le varianti vengono impostate nella categoria del prodotto di progettazione in cui si specifica il gruppo di dimensioni), la nomenclatura della regola numerica per ciascuna variante è definita nel gruppo di dimensioni. In questo caso, è possibile utilizzare l'ID prodotto della rappresentazione generale prodotto e i valori e i nomi delle dimensioni.
