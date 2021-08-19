---
title: Creare unità funzionali
description: In questo argomento viene illustrato come creare una unità funzionale in Gestione cespiti.
author: johanhoffmann
ms.date: 06/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetFunctionalLocationCopyStructure, EntAssetFunctionalLocationCreate
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e5dd5ea59b27c594752ff82428723f3afe555b5f2426a812c70e10b968c920a5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6767534"
---
# <a name="create-functional-locations"></a>Creare unità funzionali

[!include [banner](../../includes/banner.md)]

 

In questo argomento viene illustrato come creare una unità funzionale in Gestione cespiti.

Quando si crea una struttura di unità funzionali, tenere presente una volta creata una unità funzionale, non sarà possibile spostarla dalla ubicazione originale. Ciò significa che occorre valutare con attenzione la struttura di unità funzionali prima di iniziare a crearle in Gestione cespiti. Se si cambia idea su una unità funzionale la si può eliminare, purché non è ancora stata utilizzata.

Per poter utilizzare le unità funzionali, è necessario innanzitutto creare due "categorie" di unità funzionali:

- Creare *una* unità funzionale predefinita con nessuna ubicazione secondaria. Questa unità funzionale viene utilizzata solo come ubicazione predefinita per i cespiti quando si creano nuovi cespiti.  
- Creare le strutture di unità funzionali richieste per gestire i processi di manutenzione della società.

## <a name="create-a-default-functional-location"></a>Creare una unità funzionale predefinita

Quando si utilizzano le unità funzionali, iniziare creando una unità predefinita da utilizzare quando si creano nuovi cespiti. Questa unità funzionale corrisponde a quella selezionata in **Gestione cespiti** > **Impostazione** > **Parametri di gestione cespiti** > **Cespiti** > campo **Unità funzionale predefinita**. L'unità funzionale predefinita può essere utilizzata quando si creano nuovi cespiti e non è stata impostata una struttura di unità funzionali per tali cespiti.

1. Selezionare **Gestione cespiti** > **Comune** > **Unità funzionali** > **Tutte le unità funzionali**.  
2. In **Tutte le unità funzionali**, selezionare **Nuovo**.
3. Immettere un ID nel campo **Unità funzionale**, ad esempio, "0000 "o "Standard", per indicare che è una unità funzionale speciale.
4. Nel campo **Nome** immettere un nome per l'unità funzionale predefinita.
5. *Non* selezionare un padre nel campo **Padre**, lasciare vuoto il campo.
6. Nel campo **Tipo di unità funzionale**, selezionare il tipo di unità funzionale per l'unità funzionale predefinita. Per ulteriori informazioni su come impostare i tipi di unità funzionale, vedere [Tipi di unità funzionali](../setup-for-functional-locations/functional-location-types.md).
7. Selezionare **OK**. Non è necessario aggiungere ulteriori dati per questa unità funzionale perché viene utilizzata solo come ubicazione temporanea per i nuovi cespiti finché non si installano i cespiti nelle unità funzionali utilizzate dalla società.

## <a name="create-functional-locations"></a>Creare unità funzionali

Nella seguente procedura viene descritto come create le unità funzionali necessarie per la gestione della manutenzione nella società.

1. Selezionare **Gestione cespiti** > **Comune** > **Unità funzionali** > **Tutte le unità funzionali**. È possibile creare una unità funzionale dalla visualizzazione griglia o la visualizzazione dettagli.
2. Fare clic sul pulsante **Nuovo**.
3. Immettere un ID nel campo **Unità funzionale**.
4. Nel campo **Nome** immettere un nome per l'unità funzionale.
5. Se l'unità funzionale è una ubicazione secondaria in una struttura, selezionare l'ubicazione padre campo **Padre**.
6. Selezionare un tipo nel campo **Tipo di unità funzionale**.
7. Selezionare **OK**.
8. Selezionare l'unità funzionale e fare clic sul pulsante **Modifica** per aggiungere ulteriori informazioni.

>[!NOTE]
>A seconda delle impostazioni degli stati del ciclo di vita delle unità funzionali, potrebbe essere necessario creare tutte le ubicazioni secondarie per l'unità funzionale e quindi modificare lo stato del ciclo di vita delle unità funzionali prima di iniziare a installare i cespiti. Per ulteriori informazioni sull'installazione dei cespiti, vedere [Installare i cespiti nelle unità funzionali](../functional-locations/install-objects-on-functional-locations.md). Vedere [Stati del ciclo di vita delle unità funzionali](../setup-for-functional-locations/functional-location-stages.md) per ottenere ulteriori informazioni sull'impostazione degli stati del ciclo d vita delle unità funzionali.

Nella visualizzazione dettagli si vedranno delle Schede dettaglio in cui è possibile aggiungere e modificare le informazioni relative alla unità funzionale.

## <a name="general-information"></a>Informazioni generali

In questa sezione viene fornita una panoramica delle informazioni padre e figlio nella struttura di unità funzionali. Nell'**Dettagli**, è possibile visualizzare il numero di attributi del cespite, i piani di manutenzione e i cespiti correlati alla unità funzionale. Nella sezione **Inventario**, è possibile selezionare il sito e il magazzino a cui l'unità funzionale è correlata. Il sito e il magazzino viene utilizzato in relazione alle previsioni articoli degli ordini di lavoro. Durante la creazione di una previsione articoli, le informazioni di sito e magazzino dall'unità funzionale del cespite vengono utilizzate automaticamente. Nella sezione **Stato del ciclo di vita**, le informazioni sullo stato del ciclo di vita dell'unità funzionale vengono mostrate.

## <a name="installed-assets"></a>Cespiti installati

Per ulteriori informazioni sull'installazione dei cespiti, vedere [Installare i cespiti nelle unità funzionali](../functional-locations/install-objects-on-functional-locations.md). È possibile utilizzare il pulsante **Visualizza** in questa Scheda dettaglio per visualizzare ulteriori campi della scheda dettaglio. I campi **Data di inizio validità** e **Cespite secondario** possono essere visualizzati nella griglia.

## <a name="asset-attribute-requirements"></a>Requisiti degli attributi del cespite

In questa Scheda dettaglio è possibile aggiungere i requisiti specifici di attributi dei cespiti installati nella unità funzionale. Questi requisiti sono solo a scopo informativo. Non impediscono di installare i cespiti con altri requisiti di attributi. Fare clic **Aggiungi riga** e selezionare il tipo di attributo. Quindi immettere il **Valore** rilevante, selezionare una soglia nel campo **Criteri soglia** e salvare il record.

## <a name="maintenance-plans-and-maintenance-rounds"></a>Piani di manutenzione e cicli di manutenzione

Qui è possibile aggiungere i piani di manutenzione e i cicli di manutenzione all'unità funzionale, inclusa una data di inizio. I cespiti installati in una unità funzionale possono avere altri piani di manutenzione impostati. Tutti i piani di manutenzione e cicli di manutenzione si possono utilizzare per la programmazione delle voci del calendario cespiti per una untà funzionale e i relativi cespiti attualmente installati.

>[!NOTE]
>Se si aggiorna l'impostazione dei tipi di cespite, marchi di cespite e modelli di cespite nei piani di manutenzione nella visualizzazione dettagli **Tutte le unità funzionali** > Scheda dettaglio **Piani di manutenzione** dopo avere programmato i piani di manutenzione, le voci del programma di manutenzione esistenti correlate a tale unità vengono eliminate automaticamente. Per creare nuove voci di programmazione, corrispondenti all'impostazione aggiornata del piano di manutenzione per l'unità funzionale, è necessario eseguire una nuova programmazione del piano di manutenzione per tale unità funzionale. 

## <a name="address"></a>Indirizzo

Immettere l'indirizzo dell'unità funzionale sulla Scheda dettaglio **Indirizzo**. Gli indirizzi delle unità funzionali vengono ereditati, cioé se in una ubicazione secondaria non è definito indirizzo, l'indirizzo dell'unità padre viene utilizzato.

## <a name="workers"></a>Lavoratori

In questa Scheda dettaglio, è possibile aggiungere lavoratori affiliati con l'unità funzionale ed è possibile selezionare una unità funzionale come principale per il lavoratore. 

## <a name="attributes"></a>Attributi

In questa Scheda dettaglio, è possibile impostare i valori degli attributi dell'unità funzionale. Tali attributi consentono di descrivere le proprietà o caratteristiche relative alla unità funzionale, ad esempio, strutturali proprietà, il tipo di edificio, descrizioni di area, o ubicazione sopra o sotto terra.

Fare clic **Aggiungi riga** e selezionare il tipo di attributo. Dopo, immettere **Valore** relativo al tipo di attributo e salvare il record.

## <a name="financial-dimensions"></a>Dimensioni finanziarie

È possibile selezionare dimensioni finanziarie per il unità funzionale. [Tipi di unità funzionali](../setup-for-functional-locations/functional-location-types.md) sono impostabili per consentire l'aggiornamento automatico delle dimensioni finanziarie da una unità funzionale. Ciò significa che i cespiti installati su una dimensione finanziaria otterranno automaticamente le dimensioni finanziarie per l'unità funzionale. Questa opzione è utile se si desidera centri di costo diversi, a seconda delle ubicazioni.

Quando i dati relativi a **Sito**, **Magazzino**, **Indirizzo** e **Dimensioni finanziarie** vengono aggiornati in una unità funzionale padre, le unità funzionali secondarie correlate possono essere aggiornate di conseguenza si effettua questa selezione durante l'aggiornamento. Una finestra di dialogo viene aperto, fornendo le opzioni di aggiornamento.

## <a name="copy-a-functional-location-structure"></a>Copiare una struttura di unità funzionali

Se la società ha diverse unità funzionali con strutture simili, è possibile utilizzare la funzione di copia in Gestione cespiti per creare rapidamente una serie di simili gerarchie di ubicazioni. Quando si copia una specifica unità funzionale o un'intera struttura, la nuova unità o struttura ha lo stesso nome della copiata. Al termine della procedura di copia, è possibile cambiare facilmente il nome o altre impostazioni nella nuova unità funzionale, a condizione che lo stato del ciclo di vita dell'unità funzionale selezionato per la nuova unità funzionale lo consente.

1. In **Tutte le unità funzionali**, selezionare l'unità funzionale che si desidera copiare. Ad esempio, si seleziona una ubicazione superiore (padre) per copiare l'intera struttura di unità funzionali incluse le ubicazioni secondarie.
2. Fare clic sul pulsante **Copia struttura unità funzionali**. L'Ubicazione selezionata nella pagina elenco viene visualizzata nel campo **Copia da**.
3. Immettere il nome della nuova ubicazione nel campo **Nuova unità funzionale**.
4. Nel campo **Padre in cui incollare**, è necessario immettere solo un ID padre se la ubicazione da creare deve fare parte di una struttura di unità funzionali esistente.
5. Fare clic su **OK**. La nuova struttura di unità funzionali è indicata in **Tutte le unità funzionali**.

>[!NOTE]
>Quando si copia una struttura di unità funzionali, gli stati del ciclo di vita delle unità funzionali nella nuova struttura vengono impostati al "primo stato" creato per le unità funzionali. Se è possibile rinominare o eliminare una unità funzionale utilizzando i pulsanti **Rinomina** ed **Elimina** in **Tutte le unità funzionali**, dipende dallo stato del ciclo di vita corrente dell'unità funzionale.

## <a name="delete-a-functional-location"></a>Eliminare una unità funzionale

Una unità funzionale con le ubicazioni secondarie correlate può essere eliminata se non è presente alcun cespite installato nelle unità funzionali che si tenta di eliminare e se lo stato del ciclo di vita corrente dell'unità funzionale lo consente.

1. In **Tutte le unità funzionali**, selezionare l'unità funzionale che si desidera eliminare.
2. Se necessario, aggiornare l'unità funzionale allo stato del ciclo di vita che consente l'eliminazione di una unità funzionale.
3. Selezionare **Elimina**.

>[!NOTE]
>Se non è possibile eliminare una unità funzionale, è possibile gestire l'eliminazione impostando uno stato del ciclo di vita dell'unità funzionale a questo scopo. Ad esempio, è possibile impostare un fase "Scartata" "o "Eliminata "", che non deve essere una fase attiva, nel modulo **Stati del ciclo di vita delle unità funzionali**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]