--- 
title: Creare una proposta di ammortamento
description: In questa procedura viene descritto come le proposte di ammortamento batch vengono eseguite e viene illustrato come proporre l'ammortamento per i cespiti.
author: saraschi2
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 07d8cf2f1c46b99dfcd1d7c3419fe835f37c5a02
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-depreciation-proposal"></a>Creare una proposta di ammortamento

[!include [task guide banner](../../includes/task-guide-banner.md)]

In questa procedura viene descritto come le proposte di ammortamento batch vengono eseguite e viene illustrato come proporre l'ammortamento per i cespiti. In questa attività viene utilizzata la società dimostrativa USMF e il ruolo Ragioniere.


## <a name="create-depreciation-proposal"></a>Crea proposta di ammortamento
1. Andare a Cespiti > Scritture contabili > Crea proposta di ammortamento.
2. Nel campo Nome giornale di registrazione fare clic sul pulsante a discesa per aprire la ricerca.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
4. Nel campo Data finale immettere una data.
    * Selezionare l'opzione Riepilogo ammortamento per riepilogare gli ammortamenti mensili in una riga del giornale di registrazione.  
    * Ad esempio, se il valore di Data finale è il 31 marzo 2015, è possibile che venga generata la seguente descrizione: "Ammortamento dal 31 gennaio 2015". Il campo Data nelle righe proposte del giornale di registrazione verrà quindi impostato su 31 marzo 2015.  
    * La proposta di ammortamento può essere filtrata per cespite, gruppo cespite o altri criteri utilizzando l'opzione Filtro.  
    * Quando si utilizza Crea proposte di acquisizione o ammortamento per il modulo cespiti, è possibile proporre l'ammortamento in batch. Si consiglia questa procedura per le proposte di dimensioni più grandi che utilizzeranno più risorse di sistema. Se si seleziona l'opzione batch, è comunque possibile completare altre attività durante tale periodo di tempo. Quando si propone l'ammortamento in questo modo, l'ammortamento viene calcolato per i modelli di valore dei cespiti.  
5. Fare clic su Crea giornale di registrazione.

## <a name="review-depreciation-entries"></a>Verificare voci di ammortamento
1. Andare a Cespiti > Inserimenti nel giornale di registrazione > Giornale di registrazione cespiti.
2. Nell'elenco trovare e selezionare il record desiderato.
3. Fare clic su Righe.
4. Fare clic su Registra.


