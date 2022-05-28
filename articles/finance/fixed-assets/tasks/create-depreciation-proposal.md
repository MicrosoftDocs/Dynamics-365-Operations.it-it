---
title: Creare una proposta di ammortamento
description: In questo argomento viene descritto come le proposte di ammortamento batch vengono eseguite e viene illustrato come proporre l'ammortamento per i cespiti.
author: abruer
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: db747bf8e3343082feda204fc56d9608313a280e
ms.sourcegitcommit: 1d2eeacad11c28889681504cdc509c90e3e8ea86
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2022
ms.locfileid: "8716397"
---
# <a name="create-a-depreciation-proposal"></a>Creare una proposta di ammortamento

[!include [banner](../../includes/banner.md)]

In questo argomento viene descritto come le proposte di ammortamento batch vengono eseguite e viene illustrato come proporre l'ammortamento per i cespiti. In questa attività viene utilizzata la società dimostrativa USMF e il ruolo Ragioniere.


## <a name="create-a-depreciation-proposal"></a>Creare una proposta di ammortamento
1. Nel riquadro di spostamento, andare a **Cespiti > Scritture contabili > Crea proposta di ammortamento**.
2. Nel campo **Nome giornale di registrazione**, selezionare un'opzione dal menu a discesa.
3. Nel campo **Al** immettere una data.

    - Selezionare l'opzione **Riepilogo ammortamento** per riepilogare gli ammortamenti mensili in una riga del giornale di registrazione.  
    - Ad esempio, se il valore di Data finale è il 31 marzo 2015, è possibile che venga generata la seguente descrizione: "Ammortamento dal 31 gennaio 2015". Il campo **Data** nelle righe proposte del giornale di registrazione verrà quindi impostato su 31 marzo 2015.  
    - La proposta di ammortamento può essere filtrata per cespite, gruppo cespite o altri criteri utilizzando l'opzione **Filtro**.  
    - Quando si utilizza **Crea proposte di acquisizione o ammortamento per il modulo cespiti**, è possibile proporre l'ammortamento in batch. Si consiglia questa procedura per le proposte di dimensioni più grandi che utilizzeranno più risorse di sistema. Se si seleziona l'opzione batch, è comunque possibile completare altre attività durante tale periodo di tempo. Quando si propone l'ammortamento in questo modo, l'ammortamento viene calcolato per i modelli di valore dei cespiti.  

4. Selezionare **Crea giornale di registrazione**.

## <a name="review-depreciation-entries"></a>Verificare voci di ammortamento
1. Nel pannello di navigazione, andare a **Moduli > Cespiti > Inserimenti nel giornale di registrazione > Giornale di registrazione cespiti**.
2. Nell'elenco trovare e selezionare il record desiderato.
3. Selezionare **Righe**.
4. Selezionare **Registra**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
