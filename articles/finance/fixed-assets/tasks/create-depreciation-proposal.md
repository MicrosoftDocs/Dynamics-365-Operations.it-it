---
title: Creare una proposta di ammortamento
description: In questo argomento viene descritto come le proposte di ammortamento batch vengono eseguite e viene illustrato come proporre l'ammortamento per i cespiti.
author: abruer
manager: AnnBe
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 07337063c01f146c72ca6d9e0f9096907cdc9638
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142825"
---
# <a name="create-a-depreciation-proposal"></a>Creare una proposta di ammortamento

[!include [banner](../../includes/banner.md)]

In questo argomento viene descritto come le proposte di ammortamento batch vengono eseguite e viene illustrato come proporre l'ammortamento per i cespiti. In questa attività viene utilizzata la società dimostrativa USMF e il ruolo Ragioniere.


## <a name="create-a-depreciation-proposal"></a>Creare una proposta di ammortamento
1. Nel pannello di navigazione, andare a **Moduli > Cespiti > Scritture contabili > Crea proposta di ammortamento**.
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

