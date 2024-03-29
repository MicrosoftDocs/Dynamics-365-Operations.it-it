---
title: Convenzioni del leasing di cespiti
description: In questo articolo vengono descritte le convenzioni per i cespiti in leasing.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLease
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2021-1-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: f2f0e21b20a969c0847ce3a6eb167287c1d7ee3e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898271"
---
# <a name="asset-leasing-conventions"></a>Convenzioni del leasing di cespiti

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

In questo articolo vengono descritte le convenzioni per i cespiti in leasing. Le convenzioni di leasing sono utilizzate per determinare la data di inizio di un libro di leasing. Se la convenzione di leasing è impostata su **Nessuna**, la data di inizio è uguale alla data di inizio del leasing (ovvero, il valore del campo **Data di inizio leasing**). Se la convenzione di leasing è impostata su **Mese intero**, la data di inizio è il primo giorno del mese in cui cade la data di inizio del leasing.

La data di inizio determina la data di inizio del periodo per i piani di ammortamento delle passività e dei cespiti. Gli interessi passivi e le spese di ammortamento sono registrati alla data di fine periodo delle programmazioni corrispondenti. La rilevazione iniziale e la registrazione contabile di rettifica vengono registrate alla data di inizio.

> [!NOTE]
> La funzionalità per le convenzioni di leasing deve essere attivata tramite Feature Management. Nell'area di lavoro **Gestione delle funzionalità** trova e seleziona la funzione denominata **Convenzione di leasing per leasing di cespiti** quindi seleziona **Abilita ora**.

Le convenzioni di leasing sono assegnate all'impostazione di un libro cespiti di leasing.

Per visualizzare o assegnare la convenzione di leasing, segui questi passaggi.

1. Vai a **Leasing cespiti \> Imposta \> Libri di leasing**.
2. Nel campo **Convenzione di leasing**, seleziona uno dei seguenti valori.

    | Convenzione di leasing | Descrizione |
    |--------------------|-------------|
    | Nessuna priorità               | I piani di ammortamento delle passività e dei cespiti iniziano alla data di inizio del leasing, poiché la data di inizio è uguale alla data di inizio del leasing. La data di fine è un mese dopo. Questa convenzione di leasing non garantisce che gli interessi verranno registrati l'ultimo giorno di ogni mese. |
    | Mese intero         | Per i leasing che hanno una data di inizio che cade in qualsiasi momento del mese, i piani di ammortamento delle passività e dei cespiti iniziano a maturare le spese il primo giorno di quel mese. Questa convenzione di leasing garantisce che gli interessi maturino l'ultimo giorno di ogni mese per l'intero mese. |

3. Selezionare **Salva**.

Quando viene creato un leasing, la data di inizio di ciascun libro viene inserita automaticamente in base alla data di inizio immessa per il leasing e alla convenzione di leasing specificata per il libro.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
