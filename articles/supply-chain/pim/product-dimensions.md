---
title: Dimensioni prodotto
description: 'Esistono cinque dimensioni prodotto: colore, configurazione, dimensioni, stile e versione. Le dimensioni prodotto si combinano nei gruppi di dimensioni che si assegnano alle rappresentazioni generali prodotto. Le combinazioni di dimensioni prodotto determinano come si definiscono le varianti prodotto.'
author: t-benebo
manager: tfehr
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDimension, EcoResProductDimensionGroup, EcoResProductMasterDimension, RetailEcoResColor, RetailEcoResSize, RetailEcoResStyle, EcoResVersionNameLookup, RetailStyleGroupTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Retail
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: bdfd9482d30bd65cf84fae032df78e1243e05239
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4430921"
---
# <a name="product-dimensions"></a>Dimensioni prodotto

[!include [banner](../includes/banner.md)]

Esistono cinque dimensioni prodotto: colore, configurazione, dimensioni, stile e versione. Le dimensioni prodotto si combinano nei gruppi di dimensioni che si assegnano alle rappresentazioni generali prodotto. Le combinazioni di dimensioni prodotto determinano come si definiscono le varianti prodotto.

Le dimensioni prodotto sono caratteristiche che servono a identificare una variante prodotto. È possibile utilizzare combinazioni di dimensioni prodotto per definire le varianti prodotto. Per creare una variante prodotto, è necessario definire almeno una dimensione prodotto per una rappresentazione generale prodotto.

## <a name="product-variants"></a>Varianti prodotto

Le varianti prodotto vengono indicate anche con il termine articoli. Un articolo è un prodotto tangibile, non corrisponde a un servizio. È anche possibile definire una rappresentazione generale prodotto con il tipo Servizio. Utilizzando il tipo di servizio, è possibile specificare varianti prodotto che includono servizi. Ad esempio, è possibile specificare una rappresentazione generale prodotto per le varianti prodotto e consulenza per il lavoro che viene eseguito da consulenti senior e junior.

## <a name="product-dimensions"></a>Dimensioni prodotto

Una variante prodotto può essere generata in base ai valori delle dimensioni prodotto.

I valori delle dimensioni del prodotto per dimensioni, colore e stile possono essere creati nelle seguenti posizioni:

- Pagina **Dimensioni** (**Gestione informazioni sul prodotto \> Configurazione \> Gruppi di varianti e dimensioni \> Dimensioni**)
- Pagina **Colore** (**Gestione informazioni sul prodotto \> Configurazione \> Gruppi di varianti e dimensioni \> Colori**)
- Pagina **Stile** (**Gestione informazioni sul prodotto \> Configurazione \> Gruppi di varianti e dimensioni \> Stili**)

I valori delle dimensioni prodotto per la dimensione di configurazione in genere vengono creati utilizzando il configuratore prodotto o il configuratore basato su dimensioni. 

Le versioni del prodotto vengono generalmente create per versioni specifiche man mano che il prodotto si evolve durante il suo ciclo di vita. Le versioni del prodotto vengono trattate in dettaglio più avanti in questo argomento.

Le dimensioni prodotto possono essere create e gestite anche nella pagina **Dimensioni prodotto** alla quale è possibile accedere dalle posizioni seguenti:

- Vai a **Gestione informazioni sul prodotto \> Prodotti \> Rappresentazioni generali prodotto**. Nel riquadro azioni, selezionare **Dimensioni prodotto**.
- Andare a **Gestione informazioni sul prodotto \> Prodotti \> Tutti i prodotti e tutte le rappresentazioni generali prodotto**. Selezionare una rappresentazione generale prodotto. Nel riquadro azioni, selezionare **Dimensioni prodotto**.
- Andare a **Gestione informazioni sul prodotto \> Prodotti rilasciati**. Selezionare una rappresentazione generale prodotto. Nel riquadro azioni, nella scheda **Prodotto**, nel gruppo **Rappresentazione generale prodotto**, selezionare **Dimensioni prodotto**.

Il numero di varianti che è possibile creare per un articolo è limitato al numero di combinazioni possibili di dimensione prodotto.

> [!TIP]
> Quando si utilizza un prodotto in una riga ordine, ad esempio, selezionare le dimensioni prodotto per identificare la variante prodotto che si desidera utilizzare.

## <a name="example"></a>Esempio

Una società vende jeans denim. L'articolo, *Jeans*, utilizza le dimensioni prodotto colore e dimensione. I jeans vengono venduti in tre diversi colori e sei taglie diverse. I colori sono blu, nero e marrone. Le taglie sono XS, S, M, L, XL e XXL. Non tutte le taglie sono disponibili in tutti e tre i colori. Se tutte le combinazioni fossero disponibili, risulterebbero 18 tipi di jeans diversi. Tuttavia, in questo esempio, vengono prodotte solo le seguenti nove combinazioni di varianti prodotto.

| Colore | Dimensione |
|-------|------|
| Blu  | XS   |
| Blu  | D    |
| Blu  | L    |
| Nero | L    |
| Nero | L    |
| Nero | XL   |
| Marrone | L    |
| Marrone | XL   |
| Marrone | XXL  |

## <a name="the-version-product-dimension"></a>La dimensione della versione del prodotto

La versione è una dimensione del prodotto che ha lo scopo di aiutare a mantenere e tenere traccia di più versioni di un prodotto lungo la supply chain. Il rilevamento delle versioni è essenziale per il successo dei produttori che operano in un mondo caratterizzato da cicli di vita dei prodotti in costante riduzione, requisiti di qualità e affidabilità aumentati e maggiore attenzione alla sicurezza dei prodotti.

Come dimensione del prodotto standard, la versione si comporterà in modo simile alle dimensioni del prodotto esistenti (dimensione, stile, colore e configurazione). Pertanto, puoi utilizzarla per altri scopi oltre al rilevamento delle versioni del prodotto.

### <a name="turn-on-the-version-dimension"></a><a name="enable-version-dim"></a>Abilitare la dimensione della versione

#### <a name="before-you-turn-on-the-version-dimension"></a>Prima di abilitare la dimensione della versione

Quando si attiva la dimensione della versione, alcune funzionalità potrebbero non funzionare o smettere di funzionare come previsto se sono state installate altre soluzioni che aggiungono personalizzazioni alle dimensioni dello spazio pubblicitario. Affinché la dimensione della versione sia completamente funzionale, potrebbe essere necessario aggiornare tali soluzioni in modo che includano la dimensione della versione nei riferimenti alle dimensioni dell'inventario.

In fase di verifica delle soluzioni per la compatibilità con la dimensione della versione, cercare i seguenti elementi:

1. **Funzionalità:** per prima cosa è necessario valutare qualsiasi personalizzazione che coinvolge le dimensioni dell'inventario per garantire che possa funzionare insieme alla dimensione della versione.
1. **Riferimenti alle dimensioni dell'inventario:** cercare i riferimenti alle dimensioni dell'inventario (ovvero i luoghi in cui le dimensioni sono esplicitamente referenziate). Riferimenti a `InventDimId` dovrebbero funzionare per impostazione predefinita, ma controllare i riferimenti allo stile o al colore. Ad esempio, assicurarsi di controllare i seguenti elementi:

    - Chiamate API in classi estese
    - Tutti i riferimenti a dimensioni dell'inventario specifiche nel codice dell'estensione (questo codice deve indicare la dimensione della versione insieme alle dimensioni dello stile, del colore e della taglia).

1. **Riferimenti a chiamate API obsolete:** con l'introduzione della dimensione della versione, Microsoft ha cercato di rendere obsolete il minor numero possibile di API. Le poche API che sono state rese obsolete emetteranno un avviso quando si attiva la chiave di configurazione **Dimensione prodotto - versione**. Le chiamate a tali API devono essere corrette nelle soluzioni estese prima di abilitare la dimensione della versione in un sistema di produzione. Ecco le API obsolete specifiche della versione:

    - RetailTransactionServiceInventory::getProductRecordId
    - EcoResProductNumberIdentifiedProductVariantEntity::find
    - EGAISAlcoholProduction_RU::findByItemDim
    - PCVariantConfiguration::findByProductMasterAndDimensions

1. **Mappe:** se una mappa utilizza le dimensioni dell'inventario, il mapping della relazione corrispondente a queste mappe deve essere aggiornato in modo da includere la dimensione della versione. Nel modello esteso o nelle estensioni della tabella, cercare le tabelle in cui i campi includono dimensioni dell'inventario.
1. **Funzionalità di Microsoft Dynamics 365 Commerce:** dopo l'abilitazione, la dimensione della versione verrà visualizzata attraverso codice specifico di Commerce in Dynamics 365 Supply Chain Management. Tuttavia, la dimensione della versione non è ancora supportata dal database del canale di Commerce o nelle applicazioni POS o e-Commerce. Queste applicazioni specifiche di Commerce non supporteranno gli utenti che vendono/spediscono o restituiscono/ricevono inventario in base alla dimensione della versione. Le funzioni di ricerca della disponibilità di scorte non distinguono l'inventario in base alla dimensione della versione nelle app Commerce. Questo comportamento è simile al comportamento corrente della dimensione di configurazione in Commerce.

#### <a name="turn-on-the-version-dimension"></a>Abilitare la dimensione della versione

Prima di poter utilizzare la dimensione della versione, è necessario attivarla nel sistema. Questa attività richiede autorizzazioni di amministratore.

1. Andare a **Amministrazione sistema \> Aree di lavoro \> Gestione funzionalità**.
1. Attiva la funzionalità denominata *Versione dimensione prodotto*. Per ulteriori informazioni, vedere [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
1. Mettere il sistema in [Modalità manutenzione](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Accedere a **Amministrazione sistema \> Imposta \> Configurazione licenza**.
1. Nella scheda **Chiavi di configurazione**, espandere **Commercio** e selezionare la casella di controllo per **Dimensione prodotto - versione**.
1. Disabilitare la [Modalità manutenzione](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).

### <a name="areas-where-the-version-dimension-isnt-supported"></a>Aree in cui la dimensione della versione non è supportata

Le seguenti aree non supportano la dimensione della versione, perché l'introduzione di questa dimensione provocherebbe modifiche che causano un'interruzione:

- Istruzione mensile oggetto di costo
- Cache rendiconti degli oggetti di costo
- Statistiche di vendita MCR per articolo
- Cataloghi fornitore
- EcoResProductDimensionGroupEntity

Inoltre, le funzioni di creazione ed elaborazione degli ordini in Commerce (ad esempio, per ordini POS, call center ed e-commerce) non supportano la dimensione della versione. Non esiste una sequenza temporale confermata su quando gli ordini di Commerce verranno migliorati per supportarle.

### <a name="functional-characteristics-of-the-version-dimension"></a>Caratteristiche funzionali della dimensione della versione

La dimensione della versione funziona come le altre dimensioni del prodotto. Tuttavia, a causa della sua natura specifica e poiché è destinata a mantenere e tenere traccia di più versioni di un prodotto, si comporta in modo leggermente diverso. Ecco alcune differenze e somiglianze:

- **Non esiste un gruppo di versioni.**

    Sebbene il concetto di gruppi esista per dimensioni, colore e stile (gruppo di colori, gruppo di dimensioni e gruppo di stili) non esiste alcun concetto di gruppo di versioni. I gruppi consentono di predefinire i valori applicabili in modo che quando, ad esempio, si assegna un gruppo di colori a un prodotto, il prodotto può utilizzare tutti i colori in quel gruppo di colori. Questo concetto non si applica alla dimensione della versione, perché le versioni che un prodotto prende non sono predefinite quando il prodotto viene creato. Invece, le versioni vengono create durante il ciclo di vita del prodotto, quando richieste. In genere, se la forma, l'adattamento e la funzione del prodotto rimangono gli stessi, si crea una nuova versione invece di un nuovo prodotto.

- **I suggerimenti delle varianti di prodotto funzionano come fanno attualmente.**

    I suggerimenti delle varianti di prodotto creeranno suggerimenti per tutti i valori delle dimensioni della versione, proprio come fanno per le altre dimensioni. Il processo di creazione e rilascio di prodotti con versione è lo stesso dei prodotti che utilizzano altre dimensioni. Quando si crea un prodotto con versione, la prima versione (V1) verrà creata come dimensione del prodotto e le varianti verranno rilasciate. Quando il prodotto cambia ed è necessaria una nuova versione, verrà aggiunto il nuovo valore di versione (V2) e verranno rilasciate le varianti richieste. Non ci si aspetta che tutte le versioni (V1, V2 e V3) vengano create in anticipo per il prodotto.

> [!IMPORTANT]
> Se attivi e utilizzi la dimensione della versione, alcune soluzioni che fanno riferimento alle dimensioni dell'inventario potrebbero smettere di funzionare come previsto. Per confermare e risolvere questi problemi, contattare il fornitore di software indipendente (ISV) per le soluzioni interessate. Per ulteriori informazioni, vedere [Abilitare la dimensione della versione](#enable-version-dim).
