---
title: Nomenclatura di nomi e numeri di varianti prodotto
description: In questo argomento viene descritto come impostare la nomenclatura per il numero prodotto per sostituire il formato fisso [Numero rappresentazione generale prodotto - Configurazione - Dimensione - Colore - Stile].
author: roxanadiaconu
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResNomenclature, EcoResProductDimensionGroup, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 220104
ms.assetid: 3fe69fb7-5c32-423c-98a8-2f53186cda68
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: f84b6982af8b81ff83086d163a77e1c2f58ca478
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "336683"
---
# <a name="nomenclature-of-product-variant-numbers-and-names"></a>Nomenclatura di nomi e numeri di varianti prodotto

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come impostare la nomenclatura per il numero prodotto per sostituire il formato fisso [Numero rappresentazione generale prodotto - Configurazione - Dimensione - Colore - Stile]. La nuova nomenclatura ha un formato di destinazione che include il numero della rappresentazione generale prodotto, le dimensioni prodotto attive e i delimitatori di testo scelti. È inoltre possibile creare una nomenclatura per i nomi di prodotto. Infine, è anche possibile creare una nomenclatura per identificare le configurazioni create in base alla configurazione basata su vincoli del prodotto. Queste nomenclature possono includere gli attributi scelti.

Le nuove nomenclature per i numeri di varianti prodotto e i nomi di varianti prodotto consentono di includere segmenti negli identificatori per le varianti prodotto. I segmenti possono includere il nome e il numero della rappresentazione generale prodotto, i nomi e gli ID delle dimensioni prodotto, le sequenze numeriche, le costanti di testo e gli attributi. Questa funzionalità consente di trovare velocemente una variante prodotto specifica quando si crea un ordine cliente o un ordine fornitore. È possibile creare nomenclature per i numeri di varianti prodotto e i nomi di varianti prodotto utilizzando la pagina **Nomenclatura di prodotto**. Per aprire questa pagina, fare clic su **Gestione informazioni sul prodotto** &gt; **Impostazione**.

## <a name="nomenclature-of-predefined-product-variants"></a>Nomenclatura di varianti prodotto predefinite
Le varianti prodotto vengono generate per le rappresentazioni generali prodotto in base a una delle tre tecnologie di configurazione:

-   Varianti predefinite
-   Basata su vincoli
-   Basata su dimensioni

A ogni variante prodotto è associato un numero e un nome e le nomenclature dell'identificazione variante prodotto consente di selezionare i segmenti che verranno inclusi in ciascun numero di variante prodotto. È possibile selezionare i segmenti che seguono nella pagina **Nomenclatura di prodotto**:

-   Numero rappresentazione generale prodotto
-   Nome rappresentazione generale prodotto
-   Valore sequenza numerica
-   Costante testo
-   Dimensioni prodotto
    -   Nome o ID configurazione
    -   Nome o ID colore
    -   Nome o ID dimensione
    -   Nome o ID stile

Una volta definita, la nomenclatura numero di identificazione variante prodotto può essere associata a un gruppo di dimensioni prodotto. A tutte le rappresentazioni generali prodotto che fanno riferimento al gruppo di dimensioni prodotto verranno assegnati i numeri di varianti prodotto in base alla nomenclatura. Tuttavia, le nomenclature nome di variante prodotto non possono essere associate ai gruppi di dimensioni prodotto. È inoltre possibile assegnare una nomenclatura identificazione variante prodotto direttamente a una rappresentazione generale prodotto. In questo caso, alle varianti prodotto che appartengono alla rappresentazione generale prodotto verranno assegnati i numeri e i nomi di variante prodotto in base alle nomenclature.

### <a name="example"></a>Esempio

Una maglietta (TS1234) viene prodotta in tre dimensioni (S, M, L), quattro colori (rosso, verde, blu, giallo) e due stili (polo, a V). Di conseguenza, 24 varianti prodotto sono possibili = (3 × 4 × 2). Creare una nomenclatura numero di varianti prodotto contenente i segmenti seguenti:

1.  Numero rappresentazione generale prodotto
2.  Costante testo: "-"
3.  Colore
4.  Costante testo: "-"
5.  Dimensioni
6.  Costante testo: "-"
7.  Stile

In questo caso, il numero di variante prodotto per la polo piccola e rossa sarà TS1234-Red-Small-Polo.

## <a name="nomenclature-of-constraint-based-configurations"></a>Nomenclatura delle configurazioni basate su vincoli
Per le configurazioni basate su vincoli, è possibile creare una nomenclatura dedicata per la dimensione prodotto della configurazione. È possibile selezionare i segmenti che seguono nella pagina **Nomenclatura di prodotto**:

-   Valore sequenza numerica
-   Costante testo
-   Valore attributo

Ciascun componente in un modello di configurazione prodotto può avere la propria nomenclatura di configurazione. Solo gli attributi che appartengono al componente possono essere utilizzati. Gli attributi di componenti secondari o dei requisiti dell'utente non possono essere utilizzati.

### <a name="example"></a>Esempio

Un modello di configurazione prodotto ha un componente principale con due attributi:

-   Materiale (plastica, legno, acciaio)
-   Lunghezza (10...100)

Creare una nomenclatura configurazione contenente i segmenti seguenti:

1.  Valore attributo: materiale
2.  Costante testo: "AAA"
3.  Valore attributo: lunghezza

In questo caso, l'ID configurazione per il materiale legno con una lunghezza di 78 sarà WoodAAA78.

## <a name="nomenclature-of-dimension-based-configurations"></a>Nomenclatura di configurazioni basate su dimensioni
Per le configurazioni basate su dimensioni, è possibile creare una nomenclatura dedicata per la dimensione prodotto della configurazione. È possibile selezionare i segmenti che seguono nella pagina **Nomenclatura di prodotto**:

-   Valore sequenza numerica
-   Costante testo
-   Articolo gruppo di configurazioni

È possibile definire una nomenclatura di configurazione per una distinta base (DBA).

### <a name="example"></a>Esempio

La DBA è composta da quattro righe DBA divise in due gruppi di configurazioni:

-   Riga DBA: M0007, cabinet predefinito
    -   Gruppo di configurazioni: cabinet
-   Riga DBA: M0008, cabinet di fascia alta
    -   Gruppo di configurazioni: cabinet
-   Riga DBA: M0021, panno della griglia anteriore
    -   Gruppo di configurazioni: griglia anteriore
-   Riga DBA: M0022, metallo della griglia anteriore
    -   Gruppo di configurazioni: griglia anteriore

Creare una nomenclatura configurazione contenente i segmenti seguenti:

1.  Gruppo di configurazioni: cabinet
2.  Costante testo: "&"
3.  Gruppo di configurazioni: griglia anteriore

In questo caso, l'ID di configurazione per un cabinet standard con panno della griglia anteriore sarà M0007&M0021.

## <a name="nomenclature-for-a-combination-of-product-variants-and-configurations"></a>Nomenclatura per una combinazione di varianti prodotto e configurazioni
Quando si utilizza la tecnologia di configurazione basata su vincoli o su dimensioni per configurare le varianti prodotto per una rappresentazione generale prodotto, i numeri delle varianti prodotto possono includere la nomenclatura dalla dimensione di configurazione. Attenersi a questa procedura per configurare le varianti.

1.  Definire una nomenclatura del numero di varianti prodotto che includa la dimensione di configurazione nella pagina **Nomenclatura di prodotto**.
2.  Assegnare questa nomenclatura a un gruppo di dimensioni prodotto con la dimensione di configurazione.
3.  Definire una nomenclatura di configurazione per i componenti o le DBA che verranno utilizzate per la configurazione di varianti prodotto.

È inoltre possibile creare le nomenclature per i nomi di varianti prodotto. I nomi di varianti prodotto possono essere configurati per includere il nome o l'ID configurazione.

### <a name="example-for-constraint-based-configurations"></a>Esempio per le configurazioni basate su vincoli

In questo esempio è possibile utilizzare una nomenclatura del numero di varianti prodotto costituita dai seguenti segmenti:

1.  Numero rappresentazione generale prodotto
2.  Costante testo "\_"
3.  Configurazione

La nomenclatura di configurazione consiste nei seguenti segmenti:

1.  Valore attributo: materiale
2.  Costante testo: "AAA"
3.  Valore attributo: lunghezza

Immettere i seguenti valori per segmenti:

-   Numero rappresentazione generale prodotto = **M0099**
-   Materiale = **Plastic**
-   Lunghezza = **12**

In questo caso, il numero di varianti prodotto diventerà M0099\_PlasticAAA12.

### <a name="example-for-dimension-based-configurations"></a>Esempio per le configurazioni basate su dimensioni

In questo esempio è possibile utilizzare una nomenclatura del numero di varianti prodotto costituita dai seguenti segmenti:

1.  Numero rappresentazione generale prodotto
2.  Costante testo "//"
3.  Configurazione

La nomenclatura di configurazione consiste nei seguenti segmenti:

1.  Gruppo di configurazioni: cabinet
2.  Costante testo: "&"
3.  Gruppo di configurazioni: griglia anteriore

Immettere i seguenti valori per segmenti:

-   Numero rappresentazione generale prodotto = **D0123**
-   Cabinet = **M0008**
-   Griglia anteriore = **M0022**

In questo caso, il numero di varianti prodotto diventerà D0123//M0008&M0022.

## <a name="numbering-conflicts"></a>Conflitti di numerazione
In alcuni casi, è possibile impostare una nomenclatura del numero di varianti prodotto che non generi numeri univoci di varianti prodotto. Ad esempio, i numeri di varianti prodotto non sarebbero univoci se una dimensione prodotto attiva non è inclusa nella nomenclatura per una rappresentazione generale prodotto che utilizzi la tecnologia di configurazione varianti predefinita. Il modo in cui si gestiscono i conflitti varia in base alla tecnologia di configurazione.

### <a name="predefined-variants"></a>Varianti predefinite

Si verifica un errore se si tenta di creare manualmente o generare automaticamente varianti prodotto in cui più varianti prodotto finiscono con lo stesso numero. Per evitare questo scenario, è necessario utilizzare tutte le dimensioni prodotto attive nel gruppo di dimensioni prodotto. In alternativa, includere una sequenza numerica per garantire che i numeri di varianti prodotto siano univoci.

### <a name="constraint-based-configurations"></a>Configurazioni basata su vincoli

A seconda della nomenclatura, il sistema può tentare di assegnare un numero di variante prodotto non univoco a una configurazione. In questo caso viene utilizzata la sequenza numerica per la dimensione di configurazione come numero di variante prodotto e viene visualizzato un avviso. Per evitare questo scenario, includere sufficienti attributi nella nomenclature per garantire che i numeri di varianti prodotto siano univoci. È inoltre necessario assicurarsi che l'opzione **Riutilizza** sia attivata per il componente.

### <a name="dimension-based-configurations"></a>Configurazioni basate su dimensioni

Durante un passaggio del processo di configurazione viene suggerito automaticamente un valore di configurazione in base alla nomenclatura. In questa fase è possibile modificare manualmente il valore di configurazione. Quando si salva la configurazione, il sistema verifica che il valore di configurazione sia univoco. Se il valore immesso non è univoco, verrà visualizzato un messaggio di errore. Per salvare la configurazione è necessario immettere un valore univoco di configurazione.

<a name="additional-resources"></a>Risorse aggiuntive
--------

[Creare una nomenclatura del numero di prodotto per le varianti prodotto predefinite](tasks/create-product-number-nomenclature-predefined-variants-2016-11.md)

[Creare una nomenclatura di numero prodotto per le varianti prodotto configurate](tasks/create-product-number-nomenclature-product-variants_2016_11.md)

