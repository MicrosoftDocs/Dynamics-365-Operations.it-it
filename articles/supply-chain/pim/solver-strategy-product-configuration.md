---
title: Strategia risolutore per la configurazione prodotto
description: In questo articolo viene descritto come utilizzare la strategia risolutore per ottimizzare le prestazioni della configurazione prodotto.
author: t-benebo
ms.date: 02/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PCCreateProductConfigurationModel, PCProductConfigurationModelListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9b0b53da17bd106be60966d856d29d81a1e57f91
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9065519"
---
# <a name="solver-strategy-for-product-configuration"></a>Strategia risolutore per la configurazione prodotto

[!include [banner](../includes/banner.md)]

In questo articolo viene descritto come utilizzare la strategia risolutore per ottimizzare le prestazioni della configurazione prodotto.

Il concetto di strategia risolutore è stato introdotto per la prima volta nell'aggiornamento cumulativo 7 (CU7) di Microsoft Dynamics AX 2012 R2. È stato esteso nell'aggiornamento cumulativo 8 (CU8) per Microsoft Dynamics AX 2012 R3 e le app per la finanza e le operazioni, Enterprise Edition 7.3.

Il concetto di strategia risolutore ora include le seguenti strategie:

- Predefinita
- Prima domini minimi
- Dall'alto in basso
- Z3

## <a name="solver-strategy"></a>Strategia risolutore 

Un modello di configurazione prodotto può essere formulato come un [problema di soddisfacimento di vincoli (Constraint Satisfaction Problem, CSP)](http://aima.cs.berkeley.edu/2nd-ed/newchap05.pdf). Microsoft Solver Foundation Microsoft Solver Foundation (MSF) fornisce due tipi di strategia risolutore per risolvere i problemi CSP che possono essere utilizzati dai modelli di configurazione del prodotto. Queste strategie risolutore si basano sull'[euristica](https://techterms.com/definition/heuristic), utilizzata per determinare l'ordine in cui le variabili dei problemi CSP vengono prese in considerazione durante la risoluzione del problema. L'euristica può influire in modo significativo sulle prestazioni quando si risolve un problema o una classe di problemi.

La strategia del risolutore per i modelli di configurazione del prodotto determina quale risolutore viene utilizzato con l'euristica. Le strategie **Predefinita**, **Prima domini minimi** e **Dall'alto in basso** utilizzano i due risolutori di MSF, mentre la strategia **Z3** utilizza il risolutore Z3. 

Gli studi di implementazione dei clienti effettivi hanno dimostrato che una modifica della strategia del risolutore per un modello di configurazione del prodotto può ridurre il tempo di risposta da minuti a millisecondi. Pertanto, vale la pena provare diverse strategie del risolutore per trovare la strategia più efficiente per il modello di configurazione del prodotto.

## <a name="change-the-settings-for-the-solver-strategy"></a>Modificare le impostazioni per la strategia risolutore

Per modificare la strategia risolutore, nella pagina **Modelli di configurazione prodotto**, nel riquadro azioni, selezionare **Proprietà di modelli**. Quindi, nella finestra di dialogo **Modifica i dettagli del modello**, selezionare una strategia risolutore.

[![Modificare la strategia risolutore.](./media/solver-strategy.png)](./media/solver-strategy.png)

Attualmente non esiste una logica che rilevi automaticamente quale strategia risolutore sarà la strategia più efficiente per la configurazione del prodotto basata su vincoli. Pertanto, è necessario provare le strategie risolutore una ad una.

Nella tabella seguente vengono fornite indicazioni sulla strategia risolutore da utilizzare nei diversi scenari.

| Strategia risolutore      | Utilizzare la strategia in questo scenario |
|----------------------|-----------------------------------|
| Predefinita              | La strategia **Predefinita** è stata ottimizzata per risolvere i modelli in cui vengono utilizzati i vincoli di tabella. Gli studi sull'implementazione del cliente hanno dimostrato che questa strategia è la strategia più efficiente in scenari in cui i vincoli di tabella sono ampiamente utilizzati. |
| Prima domini minimi | Le strategie **Prima domini minimi** e **Dall'alto in basso** sono strettamente correlate. Gli studi sull'implementazione del cliente hanno dimostrato che la strategia **Dall'alto in basso** supera la strategia **Prima domini minimi**. Tuttavia, la strategia **Prima domini minimi** viene mantenuta nel prodotto per compatibilità con le versioni precedenti. Entrambe le strategie risolutore hanno dimostrato di essere più efficienti nel risolvere modelli che contengono diverse espressioni aritmetiche in cui non vengono utilizzati vincoli di tabella. Tuttavia, in alcuni casi, la strategia **Predefinita** supera queste due strategie. Di conseguenza, ricordare provare ogni strategia. |
| Dall'alto in basso             | Le strategie **Prima domini minimi** e **Dall'alto in basso** sono strettamente correlate. Gli studi sull'implementazione del cliente hanno dimostrato che la strategia **Dall'alto in basso** supera la strategia **Prima domini minimi**. Tuttavia, la strategia **Prima domini minimi** viene mantenuta nel prodotto per compatibilità con le versioni precedenti. Entrambe le strategie risolutore hanno dimostrato di essere più efficienti nel risolvere modelli che contengono diverse espressioni aritmetiche in cui non vengono utilizzati vincoli di tabella. Tuttavia, in alcuni casi, la strategia **Predefinita** supera queste due strategie. Di conseguenza, ricordare provare ogni strategia. |
| Z3                   | Si consiglia di utilizzare la strategia **Z3** come strategia risolutore predefinita. Se si è preoccupati per le prestazioni e la scalabilità, è possibile valutare le altre strategie. |

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica configurazione prodotto](build-product-configuration-model.md)

[Euristica](https://techterms.com/definition/heuristic)

[Problema di soddisfacimento di vincoli (CSP, Constraint Satisfaction Problem)](http://aima.cs.berkeley.edu/2nd-ed/newchap05.pdf)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
