---
title: Vincoli di tabella definiti dall&quot;utente e dal sistema
description: In questo articolo viene descritto i due tipi di vincoli di tabella per i componenti in un modello di configurazione prodotto - definito dall&quot;utente e definito dal sistema. I vincoli di tabella rappresentano le matrici delle combinazioni di attributo consentite, in cui ogni riga definisce un insieme di valori di attributi possibili.
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: PCTableConstraintAttachAttributeTree, PCTableConstraintColumnSystem, PCTableConstraintContentUserDef, PCTableConstraintDefinition, PCTableConstraintWizard
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19781
ms.assetid: 0a4ea930-b344-43a8-871e-d5cd077892c4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: b21fd97426b331726c12ea29f89817a46dd445c3
ms.openlocfilehash: 510ee819e6bc69b72df767f6cfd284230baba729
ms.lasthandoff: 03/31/2017


---

# <a name="system-defined-and-user-defined-table-constraints"></a>Vincoli di tabella definiti dall'utente e dal sistema

In questo articolo viene descritto i due tipi di vincoli di tabella per i componenti in un modello di configurazione prodotto - definito dall'utente e definito dal sistema. I vincoli di tabella rappresentano le matrici delle combinazioni di attributo consentite, in cui ogni riga definisce un insieme di valori di attributi possibili.

I vincoli di tabella rappresentano matrici delle combinazioni di attributi consentite per i componenti in un modello di configurazione del prodotto. Ogni riga nella tabella definisce un insieme di possibili valori degli attributi. È possibile dichiarare due tipi di vincoli in un modello di configurazione prodotto:

-   **Vincolo espressione**: consente di creare un'espressione che definisca le relazioni tra gli attributi per garantire che durante la configurazione prodotto possano essere selezionati solo valori compatibili.
-   **Vincolo tabella**: consente di creare una tabella che definisca tutte le combinazioni consentite per un set di attributi specificato. Sono disponibili due tipi di vincoli di tabella: vincoli di tabella definiti dall'utente e vincoli di tabella definiti dal sistema.

In questo articolo vengono descritti i vincoli di tabella definiti dall'utente e dal sistema per i componenti di un modello di configurazione prodotto.

## <a name="user-defined-table-constraints"></a>Vincoli di tabella definiti dall'utente
Un vincolo di tabella definito dall'utente è un tipo di matrice utilizzato per descrivere le combinazioni di valori di attributo definiti in base ai tipi di attributo. Ad esempio, se vengono prodotti altoparlanti, è possibile includere colonne per il rivestimento del cabinet e la griglia anteriore nel vincolo di tabella definito dall'utente. Il tipo di attributo per il rivestimento del cabinet ha quattro valori e il tipo di attributo per la griglia anteriore ha tre valori. Di conseguenza, se i vincoli non vengono utilizzati, sono possibili 4 × 3 = 12 combinazioni. Tuttavia, in questo esempio sono consentite solo sei combinazioni, come illustrato nella seguente tabella. Queste informazioni vengono visualizzate nella scheda **Combinazioni consentite** della pagina **Modifica vincolo di tabella**.

| Rivestimento del cabinet | Griglia anteriore |
|----------------|-------------|
| Nero          | Nero       |
| Nero          | Metallo       |
| Quercia            | Nero       |
| Palissandro       | Bianco       |
| Bianco          | Nero       |
| Bianco          | Bianco       |

I vincoli di tabella definiti dall'utente vengono definiti dall'input di tabella statica che funziona nello stesso modo di un vincolo di espressione. Quando si utilizza un vincolo di tabella definito dall'utente, il vantaggio consiste nel fatto che è spesso più semplice creare, comprendere e gestire tabelle rispetto a lunghi vincoli di espressione.

## <a name="system-defined-table-constraints"></a>Vincoli di tabella definiti dal sistema
Un vincolo di tabella definito dal sistema crea un mapping dinamico tra un tipo di attributo e un campo in una tabella. Quando un vincolo della tabella definito dal sistema viene incluso nel modello di configurazione prodotto, il mapping garantisce che anziché i valori del tipo di attributo vengano visualizzati i dati della tabella. Il risultato è un vincolo dinamico, poiché il contenuto della tabella può essere modificato (ad esempio, da altri moduli).  

Quando si crea un vincolo di tabella definito dal sistema, si seleziona una tabella, è possibile scegliere la query da utilizzare e quindi si associano i tipi di attributo ai campi nella tabella selezionata. I tipi di campi devono corrispondere ai tipi di attributo.  

Prima che un vincolo della tabella possa essere rese effettive in un modello di configurazione prodotto, il vincolo della tabella deve essere incluso in un vincolo su una dei componenti del modello. La procedura è creare un nuovo vincolo, selezionare il tipo di vincolo della tabella quindi selezionare la definizione del vincolo della tabella da utilizzare. Infine, tutti i campi del vincolo della tabella devono essere mappati agli attributi nel modello di configurazione prodotto.

<a name="see-also"></a>Vedere anche
--------

[Concetti chiave nei modelli configurazione prodotto](product-configuration-models.md)


