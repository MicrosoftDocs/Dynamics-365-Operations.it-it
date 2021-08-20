---
title: Il numero batch viene cancellato quando viene selezionato un nuovo ID lotto
description: Quando esamini una riga del giornale di registrazione della distinta di prelievo, il valore nel campo Numero batch viene cancellato se selezioni un nuovo valore nel campo ID lotto.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdJournalTransBOM
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: datra
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6d71720b1d3a34a31639db0f829dee300d6f96d53fd61c0a8740be9f2306d6dd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6738821"
---
# <a name="batch-number-is-cleared-when-a-new-lot-id-is-selected"></a>Il numero batch viene cancellato quando viene selezionato un nuovo ID lotto

Numero KB: 4613107

## <a name="symptoms"></a>Sintomi

Quando esamini una riga del giornale di registrazione della distinta di prelievo, il valore nel campo **Numero batch** viene cancellato se selezioni un nuovo valore nel campo **ID lotto**.

## <a name="resolution"></a>Risoluzione

Il sistema si comporta come previsto. Se modifichi l'ID lotto, modifichi il contesto dell'articolo. Pertanto, il numero batch viene reimpostato.

Per associare il numero batch a un ID lotto, devi prima impostare l'ID lotto.
