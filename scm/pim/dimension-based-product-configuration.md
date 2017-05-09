---
title: Configurazione prodotto basata su dimensioni
description: "La configurazione prodotto basata su dimensioni rappresenta una soluzione semplice per la creazione di più varianti prodotto da una singola rappresentazione generale prodotto e dalle relative distinte base."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BOMConfigRule, BOMTable, ConfigChooseFromRoute, ConfigGroup, ConfigHierarchy, EcoResDimensionBasedConfiguration
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19821
ms.assetid: 4db9890b-306b-4be7-ba98-3be2094d561f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 7fbf69dc217a2f61ec3aeda952ff221491e9385a
ms.lasthandoff: 03/31/2017


---

# <a name="dimension-based-product-configuration"></a>Configurazione prodotto basata su dimensioni

[!include[banner](../includes/banner.md)]


La configurazione prodotto basata su dimensioni rappresenta una soluzione semplice per la creazione di più varianti prodotto da una singola rappresentazione generale prodotto e dalle relative distinte base.

La configurazione prodotto basata su dimensioni è una delle tre tecnologie incorporate di configurazione prodotto. Le altre due tecnologie sono varianti predefinite e configurazione basata su vincoli. Tutte e tre le tecnologie utilizzano una rappresentazione generale prodotto come punto di inizio e consentono all'utente di creare più varianti prodotto per una rappresentazione generale prodotto.

## <a name="key-concepts"></a>Concetti chiave
La configurazione prodotto basata su dimensioni si fonde sui concetti chiave seguenti:

-   Rappresentazioni generali prodotto
-   Dimensione prodotto configurazione
-   Gruppi di configurazioni
-   Distinta base (DBA)
-   Ciclo di lavorazione di configurazione
-   Regole di configurazione

### <a name="product-masters"></a>Rappresentazioni generali prodotto

Una rappresentazione generale prodotto rappresenta il punto di partenza per qualsiasi processo di configurazione prodotto. Per la configurazione prodotto basata su dimensioni è necessaria una rappresentazione generale prodotto con questa tecnologia di configurazione specifica e un gruppo di dimensioni prodotto che include la dimensione prodotto configurazione.

### <a name="configuration-product-dimension"></a>Dimensione prodotto configurazione

La dimensione prodotto configurazione consente di identificare le varianti prodotto per una rappresentazione generale prodotto con la tecnologia di configurazione basata su dimensioni. Il valore della dimensione di configurazione viene immesso dall'utente e deve consentire l'identificazione delle singole varianti prodotto.

### <a name="configuration-groups"></a>Gruppi di configurazioni

I gruppi di configurazioni vengono definiti in un archivio centrale e possono essere utilizzati per tutti i modelli di configurazione prodotto basati su dimensioni. I gruppi di configurazioni sono associati alle singole righe DBA e tengono insieme un gruppo di righe che si escludono reciprocamente. Ciò significa che solo una riga di un gruppo può essere selezionata per una singola variante prodotto.

### <a name="bill-of-materials-bom"></a>Distinta base (DBA)

La DBA rappresenta i blocchi predefiniti per una configurazione prodotto basata su dimensioni. Deve includere tutti i prodotti diversi che possono essere utilizzati in qualsiasi variante prodotto. Ogni riga nella DBA può fare riferimento a un gruppo di configurazioni. Se una riga non fa riferimento a un gruppo di configurazioni, verrà inclusa in tutte le varianti prodotto.

### <a name="configuration-route"></a>Ciclo di lavorazione di configurazione

Il ciclo di lavorazione di configurazione determina la sequenza dei gruppi di configurazioni, che vengono visualizzati all'utente durante il processo di configurazione prodotto.

### <a name="configuration-rules"></a>Regole di configurazione

Le regole di configurazione rappresentano un meccanismo per assicurarsi che un prodotto incluso in un gruppo di configurazioni in una DBA determini l'inclusione o l'esclusione di un prodotto in un gruppo di configurazioni diverso nella stessa DBA.

## <a name="product-modeling-process"></a>Processo di modellizzazione prodotto
La sequenza naturale per generare un modello prodotto per un prodotto basato su dimensioni parte dalla definizione dei gruppi di configurazioni competenti. È importante assicurarsi che tutti i prodotti che verranno utilizzati nella DBA siano stati rilasciati alla società per la quale il modello prodotto è stato sviluppato. Con queste blocchi predefiniti configurati, l'utente può creare la DBA e assegnare gruppi di configurazione in tutte le righe DBA rilevanti. Quando la DBA è completata, un ciclo di lavorazione di configurazione può essere definito per l'ordine di gruppi di configurazioni nella sequenza appropriata. \[caption id="attachment\_282671" align="alignnone" width="1187"\][![Processo di modellizzazione prodotto basato su dimensioni](./media/dimension-based-product-modeling-process-v1.png)](./media/dimension-based-product-modeling-process-v1.png) Processo di modellizzazione prodotto basato su dimensioni\[/caption\] Se sono disponibili alcuni prodotti provenienti da gruppi di configurazione diversi che devono o non devono essere utilizzati insieme, è possibile creare regole di configurazione che imporranno tali relazioni tra i prodotti. Dopo che la DBA è stata collegata a una rappresentazione generale prodotto basata su dimensioni tramite una versione DBA ed entrambe sono state approvate e attivate, è possibile creare le configurazioni prodotto e inserire un nome per ciascuna configurazione. È possibile definire le configurazioni prima che vengano generate tutte le transazioni oppure quando si verifica la necessità di una configurazione.

### <a name="suggested-use"></a>Utilizzo suggerito

La tecnologia di configurazione basata su dimensioni è consigliata per i prodotti con variabilità limitata e la combinazione di dimensione, colore, stile e configurazione delle dimensioni prodotto standard è inadatta per l'identificazione di varianti prodotto specifiche. Un esempio potrebbe essere bicicletta con altezza di telaio, dimensione delle rotelle, i tipi del freno e ingranaggi diversi.




