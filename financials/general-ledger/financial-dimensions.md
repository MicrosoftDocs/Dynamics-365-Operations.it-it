---
title: Dimensioni finanziarie
description: Questo articolo illustra i diversi tipi di dimensioni finanziarie e come impostarle.
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DimensionDetails, DimensionValueDetails, SysTranslationDetail
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 25871
ms.assetid: af54621c-c8be-4b72-b6df-dcf886c40ce4
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 01f189b8de3f0cc707dcc54f4cde75aed95b8e3f
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="financial-dimensions"></a>Dimensioni finanziarie

[!include[banner](../includes/banner.md)]


Questo articolo illustra i diversi tipi di dimensioni finanziarie e come impostarle.

Utilizzare la pagina Dimensioni finanziarie per creare le dimensioni finanziarie che è possibile utilizzare come segmenti di conto per i piani dei conti. Sono disponibili due tipi di dimensioni finanziarie, dimensioni personalizzate e dimensioni supportate da un'entità. Le dimensioni personalizzate sono condivise tra le persone giuridiche e i valori sono immessi e gestiti dall'utente. Le dimensioni supportate da un'entità sono dimensioni i cui valori sono definiti in altre aree del sistema, ad esempio l'area dei clienti o dei punti vendita. Alcune dimensioni supportate da entità sono condivise tra le persone giuridiche, mentre alcune sono specifiche della società. 

Dopo avere creato le dimensioni finanziarie, utilizzare la pagina Valori di dimensione finanziaria per assegnare proprietà aggiuntive a ciascuna dimensione finanziaria. 

Sebbene sia possibile utilizzare le dimensioni finanziarie per rappresentare le persone giuridiche senza creare le persone giuridiche in Microsoft Dynamics 365 for Operations, le dimensioni finanziarie non sono progettate per rispondere alle esigenze operative o aziendali delle persone giuridiche. La funzionalità di contabilizzazione interunità in Microsoft Dynamics 365 for Operations è stata progettata per gestire solo le voci contabili create da ciascuna transazione. 

Prima di impostare le dimensioni finanziarie come persone giuridiche, valutare i processi aziendali nelle seguenti aree per determinare se questa impostazione verrà eseguita per l'organizzazione:

-   Inventario
-   Vendite e acquisti tra le dimensioni finanziarie e le persone giuridiche
-   Calcolo IVA e report
-   Report operativo

Di seguito sono riportate alcune limitazioni incluso quanto segue:

-   È possibile utilizzare la funzionalità IVA solo con le persone giuridiche, senza dimensioni finanziarie.
-   Alcuni report non includono le dimensioni finanziarie, pertanto non è possibile dichiarare sempre la dimensione finanziaria a meno che i report non vengano modificati.

**Dimensioni personalizzate** 

Per creare una dimensione finanziaria definita dall'utente, nel campo Usa valori da selezionare &lt;Dimensione personalizzata&gt;. È anche possibile specificare una maschera conto per limitare la quantità e il tipo di informazioni che è possibile immettere per i valori di dimensione. È possibile immettere caratteri rimanenti uguali per ciascun valore di dimensione, ad esempio le lettere o un trattino. È inoltre possibile immettere i segni di numero(\#) ed e commerciale (&) come segnaposto per le lettere e i numeri che cambieranno ogni volta che un valore di dimensione viene creato. Utilizzare un segno di numero (\#) come segnaposto per un numero e la e commerciale  (&) come segnaposto per una lettera. 

**Esempio** 

Per limitare il valore della dimensione alle lettere CC e a tre numeri, immettere CC-\#\#\# come maschera formato. Questo campo è disponibile solo se si seleziona &lt;Dimensione personalizzata&gt; nel campo Usa valori da. 

**Dimensioni supportate da un'entità** 

Per creare una dimensione finanziaria supportata da un'entità, nel campo Usa valori da selezionare un'entità definita dal sistema su cui basare la dimensione finanziaria. I valori di dimensioni finanziaria vengono creati da questa selezione. Ad esempio, per creare i valori di dimensione per i progetti, selezionare Progetti. Verrà creato un valore di dimensione per ciascun nome di progetto. Nella pagina di valori di dimensione vengono visualizzati i valori per l'entità e, se tali valori sono specifici per una società, viene visualizzata anche la società. 

**Attivazione di dimensioni** 

Attivare la dimensione finanziaria aggiorna la tabella con il nome della dimensione finanziaria e rimuove le dimensioni eliminate. È possibile immettere i valori delle dimensioni prima di attivare una dimensione finanziaria, ma una dimensione finanziaria non può essere utilizzata in alcun punto fino all'attivazione. Non è possibile ad esempio aggiungere una dimensione finanziaria a una struttura dei conti fino a quando la dimensione non sia stata attivata. Se si fa clic su Attiva, tutte le dimensioni con lo stato modificato verranno aggiornate. 

**Traduzioni** 

La pagina Traduzione testo consente di immettere il testo da visualizzare in lingue diverse per la dimensione finanziaria selezionata. Nella pagina di traduzione per un conto principale è possibile immettere il testo da visualizzare in lingue diverse per il conto principale. 

**Sostituzioni persona giuridica** 

Non tutte le dimensioni sono valide per tutte le persone giuridiche e alcune potrebbero essere pertinenti solo per un periodo di tempo specifico. In questo scenario la sezione Sostituzioni persona giuridica può essere utilizzata per identificare quali sono le società per cui è necessario sospendere la dimensione, l'identità del proprietario e il periodo di tempo durante il quale la dimensione è attiva.






