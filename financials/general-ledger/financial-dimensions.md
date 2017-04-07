---
title: Dimensioni finanziarie
description: Questo articolo illustra i diversi tipi di dimensioni finanziarie e come impostarle.
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
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
translationtype: Human Translation
ms.sourcegitcommit: 9f4d7fdd8cfa7a540fce219f6ae4792e57dfbe44
ms.openlocfilehash: f849b98cac88d182875aca88aaf04cd3575ed99f
ms.lasthandoff: 03/31/2017


---

# <a name="financial-dimensions"></a>Dimensioni finanziarie

Questo articolo illustra i diversi tipi di dimensioni finanziarie e come impostarle.

Utilizzare la pagina Dimensioni finanziarie per creare le dimensioni finanziarie che è possibile utilizzare come segmenti di conto per i piani dei conti. Sono disponibili due tipi di dimensioni finanziarie, dimensioni personalizzate e dimensioni supportate da un'entità. Le dimensioni personalizzate sono condivise tra le persone giuridiche e i valori sono immessi e gestiti dall'utente. Le dimensioni supportate da un'entità sono dimensioni i cui valori sono definiti in altre aree del sistema, ad esempio l'area dei clienti o dei punti vendita. Alcune dimensioni supportate da entità sono condivise tra le persone giuridiche, mentre alcune sono specifiche della società. 

Dopo avere creato le dimensioni finanziarie, utilizzare la pagina Valori di dimensione finanziaria per assegnare proprietà aggiuntive a ciascuna dimensione finanziaria. 

Sebbene sia possibile utilizzare le dimensioni finanziarie per rappresentare le persone giuridiche senza creare le persone giuridiche in Microsoft Dynamics 365 per le operazioni, le dimensioni finanziarie non sono progettate per soddisfare i requisiti aziendali o operativi le persone giuridiche. La funzionalità di contabilizzazione interunità in Microsoft Dynamics 365 per le operazioni è progettata per eliminare solo le voci contabili create da ciascuna transazione. 

Prima di impostare le dimensioni finanziarie come persone giuridiche, valutare i processi aziendali nelle seguenti aree per determinare se questa impostazione verrà eseguita per l'organizzazione:

-   Inventario
-   Vendite e acquisti tra le dimensioni finanziarie e le persone giuridiche
-   Calcolo IVA e report
-   Report operativo

Di seguito sono riportate alcune limitazioni incluso quanto segue:

-   È possibile utilizzare la funzionalità IVA solo con le persone giuridiche, senza dimensioni finanziarie.
-   Alcuni report non includono le dimensioni finanziarie, pertanto non è possibile dichiarare sempre la dimensione finanziaria a meno che i report non vengano modificati.

**Custom dimensions** 

Per creare una dimensione finanziaria specificata dall'utente, i valori di utilizzo del campo, selezionare la dimensione personalizzati &gt;. È anche possibile specificare una maschera conto per limitare la quantità e il tipo di informazioni che è possibile immettere per i valori di dimensione. È possibile immettere caratteri rimanenti uguali per ciascun valore di dimensione, ad esempio le lettere o un trattino. È inoltre possibile immettere i simboli di cancelletto (\#) e i nomi e commerciale (&) come segnaposto per le lettere e numeri che verranno aggiornate ogni volta che un valore viene creato. Utilizzare un simbolo cancelletto (\#) come segnaposto per un numero e la e commerciale (&) come segnaposto per una lettera. 

**Esempio** 

Per limitare il valore della dimensione in CC lettere e a tre numeri, immettere il cc\#\#\# nella maschera formato. Questo campo è disponibile solo &lt; quando si seleziona la dimensione personalizzati &gt; i valori di utilizzo nel campo. 

** Dimensioni di appoggio entità ** 

Per creare un'entità ha appoggiato la dimensione finanziaria, i valori di utilizzo del campo, selezionare un'entità definita dal sistema su cui basare la dimensione finanziaria. I valori di dimensioni finanziaria vengono creati da questa selezione. Ad esempio, per creare i valori di dimensione per i progetti, selezionare Progetti. Verrà creato un valore di dimensione per ciascun nome di progetto. Nella pagina di valori di dimensione vengono visualizzati i valori per l'entità e, se tali valori sono specifici per una società, viene visualizzata anche la società. 

** Dimensioni di attivazione ** 

Attivare la dimensione finanziaria aggiorna la tabella con il nome della dimensione finanziaria e rimuove le dimensioni eliminate. È possibile immettere i valori delle dimensioni prima di attivare una dimensione finanziaria, ma una dimensione finanziaria non può essere utilizzata in alcun punto fino all'attivazione. Non è possibile ad esempio aggiungere una dimensione finanziaria a una struttura dei conti fino a quando la dimensione non sia stata attivata. Se si fa clic su Attiva, tutte le dimensioni con lo stato modificato verranno aggiornate. 

**Translations** 

Verrà visualizzata la pagina di conversione a testo libero modo sarà possibile immettere il testo da visualizzare in lingue diverse per la dimensione finanziaria selezionata. Nella pagina di traduzione per un conto principale è possibile immettere il testo da visualizzare in lingue diverse per il conto principale. 

**Legal entity overrides** 

Non tutte le dimensioni sono valide per tutte le persone giuridiche e alcune possono solo essere pertinenti per un periodo specifico. In questo scenario la sezione Sostituzioni persona giuridica può essere utilizzata per identificare quali sono le società per cui è necessario sospendere la dimensione, l'identità del proprietario e il periodo di tempo durante il quale la dimensione è attiva.




