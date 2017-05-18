---
title: Nomenclatura del numero prodotto
description: "In questo argomento viene descritto come impostare una nomenclatura di numero prodotto in sostituzione del formato fisso, [Numero della rappresentazione generale prodotto -  Configurazione - Dimensione - Colore - Stile], con un formato di destinazione che includa il numero della rappresentazione generale prodotto, le dimensioni prodotto attive e i delimitatori di testo scelti. È anche possibile creare una nomenclatura per identificare le configurazioni create in base alla configurazione basata su vincoli del prodotto. Queste nomenclature possono includere gli attributi scelti."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: EcoResNomenclature, EcoResProductDimensionGroup, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelDetails
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 220104
ms.assetid: 31c9efb4-b5f6-4af3-b884-8f1e128469bd
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: deda2b7986333e0d865aa87e6b34b6acdc8f6a6d
ms.contentlocale: it-it
ms.lasthandoff: 04/25/2017


---

# <a name="product-number-nomenclature"></a>Nomenclatura del numero prodotto

[!include[banner](../includes/banner.md)]


In questo argomento viene descritto come impostare una nomenclatura di numero prodotto in sostituzione del formato fisso, [Numero della rappresentazione generale prodotto -  Configurazione - Dimensione - Colore - Stile], con un formato di destinazione che includa il numero della rappresentazione generale prodotto, le dimensioni prodotto attive e i delimitatori di testo scelti. È anche possibile creare una nomenclatura per identificare le configurazioni create in base alla configurazione basata su vincoli del prodotto. Queste nomenclature possono includere gli attributi scelti.

La nuova nomenclatura dei numeri di varianti prodotto consente di includere segmenti negli identificatori di varianti prodotto. I segmenti possono includere il numero della rappresentazione generale prodotto, le dimensioni prodotto, le sequenze numeriche, le costanti di testo e gli attributi. Questa funzionalità consente di trovare velocemente una variante di prodotto specifica quando si crea un ordine cliente o un ordine fornitore.

## <a name="nomenclature-of-predefined-product-variants"></a>Nomenclatura di varianti prodotto predefinite
Le varianti prodotto vengono generate per le rappresentazioni generali prodotto in base a una delle tre tecnologie di configurazione:

-   Varianti predefinite
-   Basata su vincoli
-   Basata su dimensioni

A ogni variante prodotto è associato un numero e la nomenclatura dell'identificazione variante prodotto consente di selezionare i segmenti che verranno inclusi in ciascun numero di variante prodotto. È possibile selezionare i segmenti che seguono nella pagina **Nomenclatura di prodotto**.

-   Numero rappresentazione generale prodotto
-   Valore sequenza numerica
-   Costante testo
-   Dimensioni prodotto
    -   Configurazione
    -   Colore
    -   Dimensioni
    -   Stile

Una volta definita, la nomenclatura dell'identificazione variante prodotto può essere associata a un gruppo di dimensioni prodotto. Di conseguenza, a tutte le rappresentazioni generali prodotto che fanno riferimento al gruppo di dimensioni prodotto verranno assegnati i numeri di varianti prodotto in base alla nomenclatura. È inoltre possibile assegnare una nomenclatura dell'identificativo di variante prodotto direttamente a una rappresentazione generale prodotto, nel qual caso alle varianti prodotto che appartengono a questo record verranno assegnati numeri di varianti prodotto in base alla nomenclatura.

### <a name="example"></a>Esempio

Una maglietta (TS1234) viene prodotta in 3 in diverse dimensioni (S, M, L), 4 colori differenti (rosso, verde, blu, giallo) e 2 stili (polo, V) per un totale di 24 possibili varianti prodotto. Una nomenclatura dell'identificativo di variante prodotto viene creata con i seguenti segmenti:

1.  Numero rappresentazione generale prodotto
2.  Costante di testo: "-"
3.  Colore
4.  Costante di testo: "-"
5.  Dimensioni
6.  Costante di testo: "-"
7.  Stile

Il numero di variante prodotto per la polo piccola e rossa sarà: TS1234-Red-Small-Polo.

## <a name="nomenclature-of-constraintbased-configurations"></a>Nomenclatura delle configurazioni basate su vincoli
Per le configurazioni basate su vincoli, una nomenclatura dedicata può essere generata per la dimensione di prodotto della configurazione. È possibile selezionare i segmenti che seguono nella pagina **Nomenclatura di prodotto**.

-   Valore sequenza numerica
-   Costante testo
-   Valore attributo 

Ciascun componente in un modello di configurazione prodotto può avere la propria nomenclatura di configurazione. Solo gli attributi che appartengono al componente possono essere utilizzati. Gli attributi di componenti secondari o dei requisiti dell'utente non sono disponibili.

### <a name="example"></a>Esempio

Un modello di configurazione prodotto ha un componente principale con due attributi.

-   Materiale (plastica, legno, acciaio)
-   Lunghezza (10...100)

Una nomenclatura di configurazione viene definita mediante i seguenti segmenti:

1.  Valore attributo: materiale
2.  Costante di testo: "AAA"
3.  Valore attributo: lunghezza

L'ID di configurazione per materiale di legno con una lunghezza di 78 otterrà l'ID di configurazione successivo: WoodAAA78.

## <a name="nomenclature-of-dimensionbased-configurations"></a>Nomenclatura di configurazioni basate su dimensioni
Per le configurazioni basate su dimensioni, una nomenclatura dedicata può essere generata per la dimensione di prodotto della configurazione. È possibile selezionare i segmenti che seguono nella pagina **Nomenclatura di prodotto**.

-   Valore sequenza numerica
-   Costante testo
-   Articolo gruppo di configurazioni

Una nomenclatura di configurazione può essere definita per una distinta base (DBA).

### <a name="example"></a>Esempio

Una distinta base ha 4 righe DBA divise in 2 gruppi di configurazioni.

-   Riga DBA: M0007, cabinet predefinito
    -   Gruppo di configurazioni: cabinet
-   Riga DBA: M0008, cabinet di fascia alta
    -   Gruppo di configurazioni: cabinet
-   Riga DBA: M0021, panno della griglia anteriore
    -   Gruppo di configurazioni: griglia anteriore
-   Riga DBA: M0022, metallo della griglia anteriore
    -   Gruppo di configurazioni: griglia anteriore

Una nomenclatura di configurazione viene definita mediante i seguenti segmenti:

1.  Gruppo di configurazioni: cabinet
2.  Costante di testo: "&"
3.  Gruppo di configurazioni: griglia anteriore

L'ID di configurazione per un cabinet standard con panno della griglia anteriore sarà: M0007&M0021.

## <a name="nomenclature-of-a-combination-of-product-variants-and-configurations"></a>Nomenclatura di una combinazione di varianti prodotto e configurazioni
Quando si utilizza la tecnologia di configurazione basata su vincoli o su dimensioni per configurare le varianti prodotto per una rappresentazione generale prodotto, le varianti prodotto possono ottenere i numeri di varianti prodotto che includono la nomenclatura dalla dimensione di configurazione. Attenersi a questa procedura per configurare le varianti:

1.  Definire una nomenclatura del numero di varianti prodotto che includa la dimensione di configurazione nella pagina **Nomenclatura di prodotto** .
2.  Assegnare questa nomenclatura a un gruppo di dimensioni prodotto con la dimensione di configurazione.
3.  Definire una nomenclatura di configurazione per i componenti o le DBA che verranno utilizzate per la configurazione di varianti prodotto.

### <a name="example-for-constraint-based-configurations"></a>Esempio per le configurazioni basate su vincoli

In questo esempio è possibile utilizzare una nomenclatura del numero di varianti prodotto costituita dai seguenti segmenti:

1.  Numero rappresentazione generale prodotto
2.  Costante testo '\_'
3.  Configurazione

La nomenclatura di configurazione può consistere dei seguenti segmenti:

1.  Valore attributo: materiale
2.  Costante di testo: "AAA"
3.  Valore attributo: lunghezza

È possibile immettere i seguenti valori per segmenti:

-   Numero rappresentazione generale prodotto = M0099
-   Materiale = plastica
-   Lunghezza = 12

Il numero di varianti prodotto diventerà: M0099\_PlasticAAA12.

### <a name="example-for-dimension-based-configurations"></a>Esempio per le configurazioni basate su dimensioni

In questo esempio è possibile utilizzare una nomenclatura del numero di varianti prodotto costituita dai seguenti segmenti:

1.  Numero rappresentazione generale prodotto
2.  Costante di testo: "//"
3.  Configurazione

La nomenclatura di configurazione può consistere dei seguenti segmenti:

1.  Gruppo di configurazioni: cabinet
2.  Costante di testo: "&"
3.  Gruppo di configurazioni: griglia anteriore

È possibile immettere i seguenti valori per segmenti:

-   Numero rappresentazione generale prodotto = D0123
-   Cabinet = M0008
-   Griglia anteriore = M0022

Il numero di varianti prodotto diventerà: D0123//M0008&M0022.

## <a name="numbering-conflicts"></a>Conflitti di numerazione
È possibile impostare una nomenclatura del numero di varianti prodotto che non restituisca numeri univoci di varianti prodotto. Ad esempio, ciò potrebbe verificarsi se una dimensione prodotto attiva non è inclusa nella nomenclatura per una rappresentazione generale prodotto che utilizzi la tecnologia di configurazione varianti predefinita. I conflitti vengono gestiti in modo diverso per tecnologie diverse di configurazione.

### <a name="predefined-variants"></a>Varianti predefinite

Si verificherà un errore se si tenta di generare manualmente o automaticamente varianti prodotto in cui una o più finiscono con lo stesso numero. Per evitare questo, utilizzare tutte le dimensioni prodotto attive nel gruppo di dimensioni prodotto oppure includere una sequenza numerica per accertarsi che i numeri di varianti prodotto siano univoci.

### <a name="constraint-based-configurations"></a>Configurazioni basata su vincoli

A seconda della nomenclatura, il sistema può tentare di assegnare un numero di variante prodotto non univoco a una configurazione. In questo caso verrà utilizzata la sequenza numerica per la dimensione di configurazione come numero di variante prodotto. In questo caso, verrà visualizzato un avviso. Per evitare questo, è consigliabile includere sufficiente attributi nella nomenclatura per garantire la unicità e verificare che l'opzione **Riutilizza** sia attivata per il componente.

### <a name="dimension-based-configurations"></a>Configurazioni basate su dimensioni

Il processo di configurazione include un passaggio in cui verrà suggerito automaticamente un valore di configurazione in base alla nomenclatura. In questa fase è possibile modificare manualmente il valore di configurazione. Quando si salva la configurazione, il sistema verificherà se il valore di configurazione è univoco. In caso contrario, verrà visualizzato un errore. È necessario immettere un valore univoco di configurazione per salvare la configurazione.



<a name="see-also"></a>Vedere anche
--------

[Creare una nomenclatura di numero prodotto per le varianti prodotto predefinite (guida attività)](http://ax.help.dynamics.com/en/wiki/create-a-product-number-nomenclature-for-predefined-product-variants/)

[Creare una nomenclatura di numero prodotto per le varianti prodotto configurate (guida attività)](http://ax.help.dynamics.com/en/wiki/create-a-product-number-nomenclature-for-configured-product-variants/)




