---
title: Sostituzione di materiale in fase di produzione
description: In questo argomento viene descritto come sostituire i materiali durante il processo di produzione.
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ProdBOM
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 70171
ms.assetid: ce3b11ef-550e-49b7-8942-2607c2ec3c5c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 1d6f16cad4c985a5628e2589aece8e628c83ef22
ms.lasthandoff: 03/31/2017


---

# <a name="material-substitution-in-manufacturing"></a>Sostituzione di materiale in fase di produzione

In questo argomento viene descritto come sostituire i materiali durante il processo di produzione. 

Sono disponibili tre metodi per sostituire i materiali durante il processo di produzione:

-   Per data, quando un materiale viene sostituito con un altro dopo una data specifica
-   Durante la pianificazione generale, quando un materiale in una formula viene sostituito con un altro materiale, poiché è esaurito
-   Durante la produzione, quando un materiale termina in modo imprevisto e viene sostituito con un altro materiale

## <a name="substituting-material-by-date"></a>Sostituzione di materiale in base alla data
Considerare l'opportunità dopo lo scenario: Un computer che una società viene fabbricando contiene un componente che specificata dal catalogo del fornitore in due mesi. In data di scadenza in avanti, il fornitore offrirà un nuovo componente che può essere sostituito per la precedente componente. Le date di validità iniziale e finale possono essere impostate nelle righe della distinta base (DBA). Per questo esempio, si imposta la scadenza del componente obsoleto immettendo la data di scadenza nel campo **Data finale** . Quindi, nella DBA impostare il nuovo componente sostitutivo in modo che sia valido dal giorno dopo la scadenza del componente obsoleto. A questo scopo, immettere la data nel campo **Data iniziale**.

## <a name="substituting-material-by-planning"></a>Sostituzione di materiale in base alla pianificazione
È possibile sostituire i materiali durante la pianificazione solo quando si utilizzano formule, non quando si utilizza una DBA. Si prenda in considerazione il seguente scenario: una società di produzione alimentare sta preparando una salsa utilizzando una formula con 20 ingredienti. Un ingrediente della formula può essere sostituito da uno di altri due ingredienti. Tuttavia, poiché questi due ingredienti sono più costosi dell'ingrediente preferito, la sostituzione avviene solo se l'ingrediente preferito è esaurito. Il materiale che può essere sostituito è denominato A, mentre i due materiali che possono sostituirlo sono denominati B e C. La sostituzione di materiale in base alla pianificazione è controllata dai campi **Gruppo di pianificazione** e **Priorità** nelle righe della formula. Per questo esempio, si creano righe della formula per i tre materiali e si associano le righe della formula allo stesso gruppo di pianificazione. Nell'impostazione la riga della formula per il materiale A ha la priorità superiore (numero inferiore), la riga della formula per il materiale C ha la priorità inferiore e la riga della formula per il materiale B ha una priorità intermedia tra le altre due righe. Se si richiede un articolo finito, la pianificazione generale innanzitutto determina se la domanda di materiale A può essere soddisfatta. Se la richiesta non può essere soddisfatta, la pianificazione generale si rivolge ai materiali B e C, in ordine di priorità. Se il materiale B è disponibile, verrà utilizzato dopo che un ordine batch pianificato sarà stato consolidato per la formula. Se nessuno dei materiali è disponibile, la pianificazione generale crea un ordine pianificato per il materiale A. **Nota:** quando si impostano le righe della formula in un gruppo di pianificazione, è necessario specificare una quantità solo per il materiale che ha la priorità più alta. Questa quantità verrà utilizzata per calcolare la richiesta di tutti i materiali del piano, anche i materiali con priorità inferiore. Non è possibile specificare le quantità degli articoli di priorità inferiore nel gruppo di pianificazione.

## <a name="substituting-material-during-production"></a>Sostituzione di materiale durante la produzione
Si prenda in considerazione il seguente scenario: un pezzo di piastra metallica è necessario per un'operazione di saldatura. Durante l'operazione un lavoratore di un magazzino informa l'operatore che il piatto è esaurito. Tuttavia, è stato deciso che il piatto può essere sostituito con un piatto leggermente più spesso. In quel modo l'operazione può essere finalizzata. Il materiale può essere aggiunto alla DBA per un ordine di produzione aperto. Se l'ordine di produzione ha lo stato di **Iniziato**, agli utenti viene chiesto stimare nuovamente l'ordine quando aggiungono un nuovo articolo alla DBA di produzione. Dopo avere aggiunto il materiale, è possibile creare una nuova distinta di prelievo per il nuovo articolo. Non è necessario aggiungere il nuovo materiale alla DBA di produzione. Invece, è possibile aggiungerlo direttamente alla distinta di prelievo produzione. Quindi, quando la distinta di prelievo viene registrata, il sistema aggiunge il materiale alla DBA di produzione.

