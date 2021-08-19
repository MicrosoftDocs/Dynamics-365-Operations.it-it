---
title: Il numero di formula selezionato non è approvato per un ordine batch
description: Quando tenti di stabilizzare un ordine pianificato, viene visualizzato un messaggio di errore che indica che il numero di formula selezionato non è approvato per un ordine batch.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: a41cf955d151726348bea83e52a24bc8784352c2d07268ced944e4cc6bf35491
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6712912"
---
# <a name="selected-formula-number-isnt-approved-for-a-batch-order"></a>Il numero di formula selezionato non è approvato per un ordine batch

Codice errore: PRO2614

## <a name="symptoms"></a>Sintomi

Quando tenti di stabilizzare un ordine pianificato viene visualizzato il seguente messaggio di errore:

> Il numero formula selezionato non è approvato per un ordine batch.

## <a name="cause"></a>Causa

Il sistema convalida l'operazione di stabilizzazione per assicurarsi che sia disponibile una formula approvata per l'articolo attivo. Probabilmente devi approvare la formula.

## <a name="resolution"></a>Risoluzione

Per approvare una formula, segui questi passaggi.

1. Vai a **Gestione informazioni sul prodotto \> Distinte base e formule \> Formule**.
1. Seleziona la formula rilevante.
1. Nel riquadro azioni, nella scheda **Formula**, nel gruppo **Gestisci**, seleziona **Approva formula**.
1. Nella finestra di dialogo **Approva DBA o formula** seleziona un approvatore, quindi seleziona **OK**.
