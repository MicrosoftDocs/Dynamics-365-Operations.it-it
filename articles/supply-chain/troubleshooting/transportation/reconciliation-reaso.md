---
title: È possibile aggiungere solo il conto principale come conto in Avere per motivi di riconciliazione
description: Quando imposti un motivo di riconciliazione in Gestione trasporto, puoi aggiungere solo il conto principale come conto in Avere.
author: Henrikan
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: TMSFBDetailReconcile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: c4ba48c5b6e3476c203eed2fddf053ce8af873dd6a7665df54560c8894f8c2d1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6750884"
---
# <a name="you-can-add-only-the-main-account-as-the-credit-account-for-reconciliation-reasons"></a>È possibile aggiungere solo il conto principale come conto in Avere per motivi di riconciliazione

Numero KB: 4603538

## <a name="symptoms"></a>Sintomi

Quando imposti un motivo di riconciliazione in Gestione trasporto, puoi aggiungere solo il conto principale come conto in Avere. Non è possibile aggiungere un centro di costo o qualsiasi altra dimensione come conto in Avere. Tuttavia, il conto in Dare ti consente di selezionare altre dimensioni.

## <a name="resolution"></a>Risoluzione

Se la riconciliazione non viene eseguita per pagare il fornitore ma per accreditare uno specifico conto principale, il sistema non ti consente di selezionare una dimensione finanziaria per il conto in Avere quando imposti il motivo della riconciliazione.

Se la struttura dei conti richiede uno specifico valore di dimensione finanziaria per il conto principale in Avere, il giornale di registrazione fornitore risultante non può essere registrato automaticamente perché manca il valore della dimensione finanziaria. Pertanto, devi prima specificare manualmente il conto in Avere utilizzando la pagina **Giornale di registrazione fatture**.

Poiché un valore di dimensione è richiesto per il conto in Avere, il giornale di registrazione fatture fornitore non può essere registrato automaticamente. Devi registrarlo manualmente dopo aver aggiunto manualmente il valore della dimensione al conto principale per la riga Avere.
